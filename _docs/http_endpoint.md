---
layout: docs
title: Http Endpoint
category: Edge Layer
order: 700
---

ENV variable setup

| Pattern | Description | Sample Value |
| ------- | ----------- | ------------ |
| ENDPOINTS_{ID}_TYPE | endpoint type | http |
| ENDPOINTS_{ID}_URL | url | 'http://mbp.fritz.box:8161/api/message/TEST?type=queue' |
| ENDPOINTS_{ID}_HEADER_{NR} | http header, {NR} can be arbitrary as long as it is unique | 'Authorization: Basic YWRtaW46YWRtaW4=' |

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>