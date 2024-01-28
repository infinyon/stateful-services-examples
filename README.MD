# Stateful Services Examples

This repository has working examples of functions, services, and data pipelines to get you up to speed with Stateful Services.

## Prerequisites

#### Install & update Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
rustup update
```

#### Install Fluvio & SSDK

```bash
curl -fsS https://hub.infinyon.cloud/install/install.sh | bash
fvm install 0.11.2-ssdk-preview4
```

#### Start a cluster

```bash
fluvio cluster start
```

## Examples

The examples are organized by their core functionality.

#### Window Processing
* [word-count](window-processing/word-count/Readme.md)


#### References
* [Connectors](Connectors.md)
