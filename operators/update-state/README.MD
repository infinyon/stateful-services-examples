# Update-State Operator Example

In this example, we use the `update-state` operator to collect the `temperature` values from multiple sensors into a table. The data pipeline uses `arrow-row` for the table representation.

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

Produce to sentence with and without question mark (`?`):

```bash
fluvio produce temp-sensor
```

```bash
{"id": 0, "sensor": "SF", "temperature": 54}
{"id": 1, "sensor": "LA", "temperature": 38}
{"id": 2, "sensor": "MO", "temperature": 65}
{"id": 0, "sensor": "SF", "temperature": 47}
```

Check the result in the ssdk run `>>` terminal:

```bash
>> show state save-temperature/temperature/state --table
```

```bash
 Key  sensor  temperature 
 0    SF      47          
 1    LA      38          
 2    MO      65 
```

[Install SSDK and start a Fluvio cluster]: /README.MD#prerequisites