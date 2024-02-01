# FilterMap Operator Example

Example on how to use the filter-map operator. This filter-map transform sentences longer than 10 characters, and drops all others.

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

#### 1. Start the HTTP Sink Connector

Follows the instruction in the [Connectors section](connectors) to start an HTTP-Sink connector that streams the `car` events.


#### 2. Consume from Sink Topic

Consume from `makers` topic:

```bash
fluvio consume makers
```
