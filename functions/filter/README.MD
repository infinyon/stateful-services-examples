# FilterMap Operator Example

Example of how to use the `filter` operator. In this example, the filter operation allows all sentences that have a question mark (`?`) and drops all others.

* Checkout the [dataflow.yaml](./dataflow.yaml).
* Make sure to [Install SSDK and start a Fluvio cluster].

### 1. Run Data Pipeline

With the `dataflow.yaml` file in the current directory, run the following commands:

```bash
ssdk generate
ssdk build
ssdk run
```

### 2. Test Data Pipeline

Produce to sentence with and without question mark (`?`):

```bash
fluvio produce sentences
```

```bash
Hi there!
What time is it?
```

Consume from `questions` to retrieve the result:

```bash
fluvio consume questions
```

```bash
What time is it?
```

[Install SSDK and start a Fluvio cluster]: /README.MD#prerequisites