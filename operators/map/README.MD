# Map Operator Example

Example of how to use the map operator. In this example, the map operator transforms sentences to uppercase.

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

Produce to short and long sentences:

```bash
fluvio produce sentence
```

Consume from `uppercase` to see them transformed:

```bash
fluvio consume uppercase
```

[Install SSDK and start a Fluvio cluster]: /README.MD#prerequisites