# Map Operator Example

Example of how to use the map operator. In this example, the map operator transforms sentences to uppercase.

## Step-by-step

Take a look at the [data-pipeline.yaml](./data-pipeline.yaml) to get an idea of what we're doing.

Make sure to [Install SSDK and start a Fluvio cluster].

### 1. Generate and Build

Generate and Build the data pipeline;

```bash
ssdk generate
ssdk build
```

### 2. Run the Pipeline

Run the pipeline:

```bash
 ssdk run
```

### 3. Test the Pipeline

Produce sentences:

```bash
fluvio produce sentence
```

Consume from `uppercase` to see them transformed:

```bash
fluvio consume uppercase
```
