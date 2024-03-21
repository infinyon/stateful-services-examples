# Merge Example

Here's an example of how to merge events from multiple topics into a single topic.

The example reads events from the truck and sedan topics, converts them to a string format and sends the result to the licenses topic.

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

Produce to `trucks`:

```bash
fluvio produce trucks
```

```bash
{"truck":"Ford f-150","license":"6FAF434"}
{"truck":"Dodge RAM","license":"6DUA684"}
```

Produce to `sedans`:

```bash
fluvio produce sedans
```

```bash
{"sedan":"Honda Accord","license":"4GCF223"}
{"sedan":"BMW 330","license":"5JAC844"}
```

Consume from `licenses` to see their license plates:

```bash
fluvio consume licenses -B
```

```bash
"6FAF434"
"6DUA684"
"4GCF223"
"5JAC844"
```


[Install SSDK and start a Fluvio cluster]: /README.MD#prerequisites