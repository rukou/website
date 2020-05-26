---
layout: docs
title: Echo Endpoint
category: Edge Layer
order: 699
---

The Echo enpoint takes an incoming message and reply with the same data. This endpoint type is mainly used for connection testing and benchmarking.

### ENV variable setup

| Pattern | Cardinality | Description | Sample Value |
| ------- | ----------- | ------------ |
| ENDPOINTS_{id}_TYPE | required | endpoint type | echo |

<br>
### Sample configuration

    EDGE_HOSTS_1: api.domain.tld
    ROUTES_MY-PUBSUB-ROUTE_TYPE: google-pubsub
    ROUTES_MY-PUBSUB-ROUTE_EDGE2LOCALTOPIC: projects/project-id/topics/edge2local
    ROUTES_MY-PUBSUB-ROUTE_LOCAL2EDGEPREFIX: local2edge
    ROUTES_MY-PUBSUB-ROUTE_SERVICEACCOUNT: '{...}'
    ENDPOINTS_ECHO1_TYPE: echo
    ENDPOINTS_ECHO1_SELECTOR: 'header["X-HTTP-HOST"]=="api.domain.tld"'
    ENDPOINTS_ECHO1_ROUTE: MY-PUBSUB-ROUTE

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>