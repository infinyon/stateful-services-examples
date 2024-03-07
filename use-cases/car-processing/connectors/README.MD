# Connector to Generate Sentences

Use an http-source streaming connector to read cars from the InfinyOn synthetic data server. 

The connector configuration file is located at [car-connector.yaml](car-connector.yaml).

### 1. Download HTTP Source Connector

```bash
cdk hub download infinyon/http-source@0.3.3
```

### 2. Start the car connector

```bash
cdk deploy start --ipkg infinyon-http-source-0.3.3.ipkg -c car-connector.yaml
```

### 2. Start the licenses connector

```bash
cdk deploy start --ipkg infinyon-http-source-0.3.3.ipkg -c license-connector.yaml
```


### 3. Checkout  car events

```bash
fluvio consume cars
```

### 4. Stop the connector

```bash
cdk deploy shutdown --name car-connector
```