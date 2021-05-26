Ansible AMQ Streams Role [![Build Status](https://travis-ci.com/saiello/amq-streams.svg?branch=master)](https://travis-ci.com/saiello/amq-streams)
---

A role to install Red Hat AMQ Streams. Examples of its usage are collected in [amq-streams playbook examples](https://github.com/saiello/amq-streams-playbook-examples) 


## Zookeeper Configuration

When `amq_streams_zookeeper_id` is defined installation will be considered as multihost and zookeeper properties are generated according to it. 


## Kafka Configuration

Kafka properties can be defined using the dictionary `amq_streams_kafka_configurations`. 
Each entry will be a property into the server.properties configuration file.

For example:

```
amq_streams_kafka_configurations:
  listeners: 'SSL://localhost:9092'
  inter.broker.listener.name: SSL
  ssl.keystore.location: "/etc/certs/kafka.server.keystore.jks"
  ssl.keystore.password: changeit
```

The field `zookeeper.connect` of kafka brokers configuration will be automatically generated unless the `amq_streams_kafka_zookeeper_connect` variable will be provided.
