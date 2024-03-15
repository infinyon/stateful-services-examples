# Map Operator Example

Example of how to use the `map` operator. In this example, the map operator transforms masks SSN numbers in a user record.

* Checkout the [dataflow.yaml](./dataflow.yaml).
* Make sure to [Install SSDK and start a Fluvio cluster].

### 1. Run Data Pipeline

With the `dataflow.yaml` file in the current directory, run the following commands:

```bash
ssdk generate
ssdk build
ssdk run
```

### 2. Test Data Pipeline

Produce to `users`:

```bash
fluvio produce users
```

```bash
{"name": "Alice", "ssn": "222-333-5555"}
{"name": "Bob", "ssn": "444-666-7777"}
```

Consume from `users-public` to see them transformed:

```bash
fluvio consume users-public
```

```bash
{"name":"Alice","ssn":"***-***-****"}
{"name":"Bob","ssn":"***-***-****"}
```

[Install SSDK and start a Fluvio cluster]: /README.MD#prerequisites