# HTTP Callout Example

HTTP Callout shows how to call external HTTP servers from inside the operators. In this example, we will read `car` events and send requests to an HTTP server for additional information about the `maker`.

<p align="center">
 <img width="700" src="img/http-callout.jpg">
</p>

The `car` events are generated via an [HTTP-Source connector](connectors).

## Pipeline Primitives

The pipeline uses the following primitives:
* _map_
* _capabilities_
  * _http_


## Step-by-step

Take a look at the [dataflow.yaml](./dataflow.yaml) to get an idea of what we're doing.

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
 ssdk run --ui
```

Use `--ui` to open the Studio.


### 3. Test the Pipeline

#### 1. Start the HTTP Sink Connector

Follows the instruction in the [Connectors section](connectors) to start an HTTP-Sink connector that streams the `car` events.


#### 2. Consume from Sink Topic

Consume from `makers` topic:

```bash
fluvio consume makers
```

#### 3. Check the state

Check the progress by reading the internal offset.

```bash
show state lookup-car-maker/cars/topic.offset
```

[Install SSDK and start a Fluvio cluster]: /README.MD#prerequisites
