# Stateful Services Examples

This repository has data pipeline examples to get you up to speed quickly with Stateful Services.

## Prerequisites

#### Install & update Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
rustup update
```

#### Install Fluvio & SSDK

```bash
curl -fsS https://hub.infinyon.cloud/install/install.sh | bash
fvm install ssdk-preview6
```

#### Start a cluster

```bash
fluvio cluster start
```

## Use Cases

Use cases using data pipelines:

* [bank-processing](/use-cases/bank-processing/)
* [http-callout](//use-cases/http-callout/)
* [openai-callout](//use-cases/openai-callout/)
* [word-counter](//use-cases/word-counter/)

## Functions

Simple functionality centric examples.

* [map](/functions/map/)
* [filter](/functions/filter/)
* [filter-map](/functions/filter-map/)
* [flat-map](/functions/flat-map/)
* [update-state](/functions/update-state/)


## References
* [connectors](connectors.md)
