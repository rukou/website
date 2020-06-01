---
layout: docs
title: Echo Endpoint
category: Edge Layer
order: 699
---

The Echo enpoint takes an incoming message and replies with the same data. This endpoint type is mainly used for connection testing and benchmarking.

The Echo can be either performed by the Edge Layer or by the Local Layer.

### ENV variable setup

| Pattern | Cardinality | Description | Sample Value |
| ------- | ----------- | ------------ |
| ENDPOINTS_{id}_TYPE | required | echo-on-edge-layer: echoes the message on the edge layer<br>echo-on-local-layer: echoes the message on the local layer | echo-on-local-layer |

<br>

### Sample configuration

#### Echo on Edge Layer

    HOSTS_1_DOMAIN: api.domain.tld
    ENDPOINTS_1_TYPE: echo-on-edge-layer
    ENDPOINTS_1_SELECTOR: 'header["X-HTTP-HOST"]=="api.domain.tld"'

#### Echo on Local Layer

    HOSTS_1_DOMAIN: api.domain.tld
    ROUTES_1_TYPE: google-pubsub
    ROUTES_1_ALIAS: MY-PUBSUB-ROUTE
    ROUTES_1_EDGE2LOCALTOPIC: projects/project-id/topics/edge2local
    ROUTES_1_LOCAL2EDGEPREFIX: local2edge
    ROUTES_1_SERVICEACCOUNT: '{...}'
    ENDPOINTS_1_TYPE: echo-on-local-layer
    ENDPOINTS_1_SELECTOR: 'header["X-HTTP-HOST"]=="api.domain.tld"'
    ENDPOINTS_1_ROUTE: MY-PUBSUB-ROUTE

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>