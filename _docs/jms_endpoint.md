---
layout: docs
title: Jms Endpoint
category: Edge Layer
order: 700
---

ENV variable setup

| Pattern | Cardinality | Description | Sample Value |
| ------- | ----------- | ------------ |
| ENDPOINTS_{ID}_TYPE | required | endpoint type | jms |
| ENDPOINTS_{ID}_INITIALFACTORY | required | jndi initial context factory | 'http://mbp.fritz.box:8161/api/message/TEST?type=queue' |
| ENDPOINTS_{ID}_PROVIDERURL | required | url | tcp://mbp.fritz.box:61616 |
| ENDPOINTS_{ID}_DESTINATION | required | queue/topic name | dynamicQueues/TEST |
| ENDPOINTS_{ID}_USER | optional | user name | admin |
| ENDPOINTS_{ID}_PASSWORD | optional | password | supersecret |
| ENDPOINTS_{ID}_CONNECTIONFACTORY | optional | Connection factory, if not given, defaults to 'ConnectionFactory' | QueueConnectionFactory |

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>