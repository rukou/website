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
| EDGE_HOSTS_{id} | DNS name, multiple entries can be create through different ids. | api.domain.tld |
| ROUTESCONFIG_MY-PUBSUB-ROUTE_TYPE |
| ROUTESCONFIG_MY-PUBSUB-ROUTE_EDGE2LOCALTOPIC |
| ROUTESCONFIG_MY-PUBSUB-ROUTE_LOCAL2EDGEPREFIX |
| ROUTESCONFIG_MY-PUBSUB-ROUTE_SERVICEACCOUNT |

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>