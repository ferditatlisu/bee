<h1 align="center">Bee</h1>

<p align="center">
  <a href="https://github.com/ferditatlisu/bee/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License" />
  </a>
</p>

The Bee is a useful tool for managing Kafka commands, viewing messages within topics, searching for specific keywords, and copying topics.
{{Medium link}}

## Release Notes

* [Bee-api](https://github.com/ferditatlisu/bee-api/blob/main/README.md)
* [Bee-ui](https://github.com/ferditatlisu/bee-ui/blob/main/README.md)
* [Bee-pod master api](https://github.com/ferditatlisu/bee-pod-master/blob/main/README.md)
* [Bee-search](https://github.com/ferditatlisu/bee-search/blob/main/README.md)
* [Bee-copy](https://github.com/ferditatlisu/bee-copy/blob/main/README.md)

## Getting Started

To prepare for deployments, it is necessary to assign specific values to environment keys. Once this is done, the deployment can be initiated.

    kubectl create pod ./.deploy/bee-ui.yaml

###

    kubectl create pod ./.deploy/bee-api.yaml

###

    kubectl create pod ./.deploy/bee-pod-master.yaml

###

## Environment Variables

SERVICE_ACCOUNT_NAME has to create & delete permissions.

```yaml
- name: SERVICE_ACCOUNT_NAME
  value: bee-sa
```

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: {NAMESPACE_SAME_WITH_ENVIRONMENT}
  name: bee-role
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["delete", "create"]
---
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: bee-role-binding
  namespace: {NAMESPACE_SAME_WITH_ENVIRONMENT}
subjects:
- kind: ServiceAccount
  name: bee-sa
  namespace: {NAMESPACE_SAME_WITH_ENVIRONMENT}
roleRef:
  kind: Role
  name: bee-role 
  apiGroup: rbac.authorization.k8s.io

```

###

Example of secure Kafka config

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
