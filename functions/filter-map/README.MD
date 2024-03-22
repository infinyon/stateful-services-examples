# FilterMap Operator Example

Example of how to use the `filter-map` operator. In this example, the filter-map operation transforms sentences over 10 characters in length to uppercase and drops all others.

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

Produce to short and long sentences:

```bash
fluvio produce sentences
```

```bash
say hello
say hello world
```

Consume from `capitalized` to retrieve the result:

```bash
fluvio consume capitalized
```

```bash
SAY HELLO WORLD
```

[Install SSDK and start a Fluvio cluster]: /README.MD#prerequisites
