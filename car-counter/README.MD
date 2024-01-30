# Car Count Pipeline

Car count data pipeline uses the http-source conector to stream synthetic data from `data.infinyon.com` at a rate of 2 events per second. The events send car data from two semaphores, Saratoga and Sunnyvale. and the data pipeline performs the following operations:

* Enrich car events with maker information (http call-out operation)
* Count all cars per maker continent for all locations (unbounded processing)
* Count cars based per maker for all locations (window processing - per minute)
* Computer average speed for each location (window processing - per minute)
* Detect Speeding - if a car is driving faster than 60 mph for all locations (window processing - per minute)
* Detect Annomaly - if 2 cars of different types have the same license plate per location (window processing - per minute)
* Filter out German cars (filter operation)
* Divide the events into 2 streams Saratoga, Sunnyvale (split operation)

## Prerequisites

* Follow the instructions on the front-page to [Install SSDK & Start a Cluster].

## Step-by-step

Take a look at the [data-pipeline.yaml](./data-pipeline.yaml) to get an idea of what we're doing.


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

