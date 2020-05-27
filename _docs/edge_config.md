---
layout: docs
title: Configuration
category: Edge Layer
order: 200
---
The edge layer is build for a kubernetes runtime. Therefore all configuration is handled through environment variables.

These can either be provided through ConfigMap or single variables.

ENV variable setup

| Pattern | Description | Sample Value |
| ------- | ----------- | ------------ |
| EDGE_HOSTS_{HID} | DNS name, multiple entries can be create through different ids. | api.domain.tld |
| ROUTES_{RID}_TYPE | type of the route | google-pubsub |
| ROUTES_{RID}_{property} | configuration for the route | |
| ENDPOINTS_{EID}_TYPE | type of the endpoint | echo |
| ENDPOINTS_{EID}_SELECTOR | selector for this enpoint | header["X-HTTP-HOST"]=="api.domain.tld" |
| ENDPOINTS_{EID}_ROUTE | id of the previously defined route | MY-ROUTE-1 |

<br>
Technology specific samples are avaible in the endpoint section.

* [Echo Endpoint](echo_endpoint)
* [Http Endpoint](http_endpoint)
* [Jms Endpoint](jms_endpoint)
* [Kafka Endpoint](kafka_endpoint)

<br>
<br>

For more sample, please check out our sample section managed through the following repo.

[https://github.com/rukou/deployment-samples/tree/master/edge_layer](https://github.com/rukou/deployment-samples/tree/master/edge_layer)

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>