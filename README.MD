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
fvm install 0.11.3-ssdk-preview5
```

#### Start a cluster

```bash
fluvio cluster start
```

## Data Pipeline Examples

* [bank-processing](/pipelines/bank-processing/)
* [http-callout](/pipelines/http-callout/)
* [word-counter](/pipelines/word-counter/)

## Operator Examples

* [map](/operators/map/)
* [filter-map](/operators/filter-map/)

## References
* [connectors](connectors.md)
