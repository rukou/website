---
layout: docs
title: Jms Endpoint
category: Edge Layer
order: 700
---

ENV variable setup

| Pattern | Cardinality | Description | Sample Value |
| ------- | ----------- | ------------ |
| ENDPOINTS_{id}_TYPE | required | endpoint type | jms |
| ENDPOINTS_{id}_INITIALFACTORY | required | jndi initial context factory | 'http://mbp.fritz.box:8161/api/message/TEST?type=queue' |
| ENDPOINTS_{id}_PROVIDERURL | required | url | tcp://mbp.fritz.box:61616 |
| ENDPOINTS_{id}_DESTINATION | required | queue/topic name | dynamicQueues/TEST |
| ENDPOINTS_{id}_USER | optional | user name | admin |
| ENDPOINTS_{id}_PASSWORD | optional | password | supersecret |
| ENDPOINTS_{id}_CONNECTIONFACTORY | optional | Connection factory, if not given, defaults to 'ConnectionFactory' | QueueConnectionFactory |

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>