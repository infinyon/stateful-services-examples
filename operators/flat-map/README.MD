# FlatMap Operator Example

Example of how to use the `flat-map` operator. In this example, the flat-map operator converts sentences into words.

* Checkout the [data-pipeline.yaml](./data-pipeline.yaml).
* Make sure to [Install SSDK and start a Fluvio cluster].

### 1. Run Data Pipeline

With the `data-pipeline.yaml` file in the current directory, run the following commands:

```bash
ssdk generate
ssdk build
ssdk run
```

### 2. Test Data Pipeline

Produce sentences:

```bash
fluvio produce sentences
```

```bash
This is a test
```

Consume from `words` to see them transformed:

```bash
fluvio consume words
```

```bash
This
is
a
test
```

[Install SSDK and start a Fluvio cluster]: /README.MD#prerequisites