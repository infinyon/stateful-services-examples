# Stateful Services Training Guide

Working examples to help Fluvio users come up to speed with Stateful Services.

### Prerequisites

1. Install & update Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
rustup update
```

2. Install Fluvio & SSDK

```bash
curl -fsS https://hub.infinyon.cloud/install/install.sh | bash
```

3. Setup SSDK

```bash
ssdk setup
```

4. Start a cluster

```bash
fluvio cluster start
```


## Operators

Examples on how to use the operators:

* [filter](operators/filter.md)
* [map](operators/map.md)
* [filter-map](operators/filter-map.md)

## Workflows