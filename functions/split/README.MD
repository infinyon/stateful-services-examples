# Split Example

Here's an example of how to split traffic from one to multiple topics.

The example splits car events into trucks and sedans based on their category while converting the record format to conform to the schema of the receiving topics. 

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

Produce to `cars`:

```bash
fluvio produce cars
```

```bash
{"car":"Honda Accord","category":"sedan","license":"4GCF223"}
{"car":"Ford f-150","category":"truck","license":"6FAF434"}
{"car":"BMW 330","category":"sedan","license":"5JAC844"}
{"car":"Dodge RAM","category":"truck","license":"6DUA684"}
```

Consume from `trucks` to see trucks:

```bash
fluvio consume trucks
```

```bash
{"truck":"Ford f-150","license":"6FAF434"}
{"truck":"Dodge RAM","license":"6DUA684"}
```

Consume from `sedans` to see sedans:

```bash
fluvio consume sedans
```

```bash
{"sedan":"Honda Accord","license":"4GCF223"}
{"sedan":"BMW 330","license":"5JAC844"}
```

[Install SSDK and start a Fluvio cluster]: /README.MD#prerequisites