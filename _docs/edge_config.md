---
layout: docs
title: Configuration
category: edge layer
order: 200
---
The edge layer is build for a kubernetes runtime. Therefore all configuration is handled through environment variables.

These can either be provided through ConfigMap or single variables.
Each set of configuration can either be provided through YAML or single variable entries.

YAML setup

ENV variable setup

| Pattern | Description | Sample Value |
| ------- | ----------- | ------------ |
| ROUTESCONFIG_MY-PUBSUB-ROUTE_TYPE |
| ROUTESCONFIG_MY-PUBSUB-ROUTE_EDGE2LOCALTOPIC |
| ROUTESCONFIG_MY-PUBSUB-ROUTE_LOCAL2EDGETOPIC |
| ROUTESCONFIG_MY-PUBSUB-ROUTE_LOCAL2EDGESUBSCRIPTION |
| ROUTESCONFIG_MY-PUBSUB-ROUTE_SERVICEACCOUNT |