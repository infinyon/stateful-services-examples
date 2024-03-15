# Connectors to Generate Licneses & Car Events

Use http-source connector to install license plates and read cars from the InfinyOn synthetic data server. 

### Prerequisites

Download HTTP Source Connector

```bash
cdk hub download infinyon/http-source@0.3.3
```

### Start the licenses connector

Checkout the connector configuration file [license-connector.yaml](license-connector.yaml) for context.

Start the connector:

```bash
cdk deploy start --ipkg infinyon-http-source-0.3.3.ipkg -c license-connector.yaml
```

This connector refreshes the licenses every hour. Let's what it has downloaded:

```bash
fluvio consume licenses -Bd
```


### Start the car connector

Checkout the connector configuration file [car-connector.yaml](car-connector.yaml) for context.

```bash
cdk deploy start --ipkg infinyon-http-source-0.3.3.ipkg -c car-connector.yaml
```

The cars connector receives two car events every second. Let's check it out

```bash
fluvio consume cars
```

User <Ctrl-C> to exit


### Clean-up

Stop the connectors:

```bash
cdk deploy shutdown --name car-connector
cdk deploy shutdown --name license-connector
```
