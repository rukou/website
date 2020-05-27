---
layout: docs
title: Kafka Endpoint
category: Edge Layer
order: 710
---

ENV variable setup

| Pattern | Cardinality | Description | Sample Value |
| ------- | ----------- | ------------ |
| ENDPOINTS_{id}_TYPE | required | endpoint type | kafka |
| ENDPOINTS_{id}_BOOTSTRAPSERVERS | required | bootstrap servers | localhost:9092 |
| ENDPOINTS_{id}_TOPIC | required | name of the topic | topic1 |

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>