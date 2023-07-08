# Bee

The Bee is a tool that helps manage Kafka commands, view topics' messages, search any keyword in Topics, copy one topic to another, and so on. I will highlight so many features, but first, let's start with the beginning story of Bee.
{{Medium link}}


## Getting Started
    kubectl create pod ./.deploy/bee-ui.yaml
###
    kubectl create pod ./.deploy/bee-api.yaml
###
    kubectl create pod ./.deploy/bee-pod-master.yaml
###


## Configs
    POD MASTER API: Service account name has to be create & delete permissions.
        - name: SERVICE_ACCOUNT_NAME
            value: bee-sa
### 
    Secure Kafka:
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
####

