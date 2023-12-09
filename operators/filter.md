# Operator `filter`

Filter operator takes a record and return a `bool`, if true the record is passed to the next operator, if false the record is dropped.

## Example

In the following example, we use the filter operator to remove all works shorter than four letters.

### 1. Create workflow file

Create a file `filter-example.yaml` and copy/paste the following configuration:

```yaml
apiVersion: 0.1.0

meta:
  name: filter-example
  version: 0.1.0
  namespace: my-org

config:
  converter: json
  consumer:
    default_starting_offset:
      value: 0
      position: End

types:
  word:
    type: string

topics:
  words:
    name: words
    schema:
      value:
        type: word
  long-words:
    name: long-words
    schema:
      value:
        type: word

services:

  long-words-service:
    source:
      type: topic
      id: words
    transforms:
      steps:
        - operator: filter
          uses: filter-words-fn
          inputs:
            - name: word
              type: word
          output:
            type: bool
          run: |
            if word.len() < 4 {
              println!("Too short -> {} - filtered out", word);
              Ok(false)
            } else {
              Ok(true)
            }
    sink:
      type: topic
      id: long-words
```

### 2. Add source & target topics

Use fluvio CLI to create `words` and `long-words` topics on your cluster:

```bash
fluvio topic create words
fluvio topic create long-words
```

### 3. Build and Run Project

Use SSDK generate to build build the project:

```bash
ssdk generate -w ./filter-example.yaml
```

In the new project directory, compile and run

```bash
cd filter-example
ssdk build
ssdk run
```

### 4. Test the Project

Produce on `words`:

```bash
fluvio produce words
```

Produce the following words:

```bash
"one"
"two"
"three"
"four"
"five"
"six"
"seven"
"eight"
"nine"
"ten"
```

Watch `ssdk` window for our println messages:

```bash
Too short -> one - filtered out
Too short -> two - filtered out
Too short -> six - filtered out
Too short -> ten - filtered out
```

Read from `long-words` to see the result:

```bash
fluvio consume long-words -B
```

Returns only long words:

```bash
"three"
"four"
"five"
"seven"
"eight"
"nine"
```


## Clean-up

Stop the `ssdk` runtime:
`````
1. Stop ssdk processing; type `stop` or `<ctrl>-c`
2. Delete topics `words` & `long-words`
3. Remove `filter-example` directory