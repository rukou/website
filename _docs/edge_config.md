---
layout: docs
title: Configuration
category: Edge Layer
order: 200
---
The edge layer is build for a kubernetes runtime. Therefore all configuration is handled through environment variables.

These can either be provided through ConfigMap or single variables.

ENV variable setup

| Pattern | Cardinality | Description | Sample Value |
| ------- | ----------- | ----------- | ------------ |
| HOSTS_{ID}_DOMAIN | optional | DNS name, multiple entries can be create through different ids. If no record is present, no domain filtering is performed | api.domain.tld |
| HOSTS_{ID}_AUTH | optional | Triggers authentication on this host. Allowed values are 'none','apikey'. The default is 'none'. | apikey |
| HOSTS_{ID}_APIKEY_{ID2} | optional | Configure API keys used for authenticating requests. | E37184D3-14FC-48ED-8B41-7A40AB750375 |
| ROUTES_{ID}_TYPE | required | type of the route | google-pubsub |
| ROUTES_{ID}_{property} | optional | configuration for the route | |
| ENDPOINTS_{ID}_TYPE | required | type of the endpoint | echo-on-local-layer |
| ENDPOINTS_{ID}_SELECTOR | optional | Selector for this enpoint. If none was given, the condition is always true. | header["X-HTTP-HOST"]=="api.domain.tld" |
| ENDPOINTS_{ID}_ROUTE | optinal | ID of the previously defined route. If none was given, the first route is chosen. | 1 |

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