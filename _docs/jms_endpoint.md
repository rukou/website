---
layout: docs
title: Jms Endpoint
category: Edge Layer
order: 700
---

ENV variable setup

| Pattern | Description | Sample Value |
| ------- | ----------- | ------------ |
| ENDPOINTS_{id}_TYPE | endpoint type | jms |
| ENDPOINTS_{id}_INITIALFACTORY | jndi initial context factory | 'http://mbp.fritz.box:8161/api/message/TEST?type=queue' |
| ENDPOINTS_{id}_PROVIDERURL | url | tcp://mbp.fritz.box:61616 |
| ENDPOINTS_{id}_DESTINATION | queue/topic name | dynamicQueues/TEST |
| ENDPOINTS_{id}_USER | user name | admin |
| ENDPOINTS_{id}_PASSWORD | password | supersecret |

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>