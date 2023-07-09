<h1 align="center">Bee</h1>

<p align="center">
  <a href="https://github.com/ferditatlisu/bee/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License" />
  </a>
</p>

The Bee is a useful tool for managing Kafka commands, viewing messages within topics, searching for specific keywords, and copying topics.
{{Medium link}}

## Getting Started

To prepare for deployments, it is necessary to assign specific values to environment keys. Once this is done, the deployment can be initiated.

    kubectl create pod ./.deploy/bee-ui.yaml

###

    kubectl create pod ./.deploy/bee-api.yaml

###

    kubectl create pod ./.deploy/bee-pod-master.yaml

###

## Configs

SERVICE_ACCOUNT_NAME has to create & delete permissions.

```yaml
- name: SERVICE_ACCOUNT_NAME
  value: bee-sa
```

###

Example of secure Kafka

```yaml
- name: KAFKA_CONFIGS
  value: |
    [
      {
        "id" : 0,
        "name": "Secure Kafka",
        "host": "kafka-s-broker-01.bee.com:9093",
        "userName": "username",
        "password": "password",
        "certificate": ["-----BEGIN CERTIFICATE-----",
      "MIIDkzCCAnugAwIBAgIJAObeebeeebeeebeeebeeebeeebeeebeeebeeebeebeee",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "beebebebebebebebebebebebebebebebebebebebebebebeebebebebebebebebe",
      "bgu9XWttsQ==",
      "-----END CERTIFICATE-----"]
      }
    ]
```
