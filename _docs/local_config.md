---
layout: docs
title: Configuration
category: local layer
order: 200
---
The local layer is build for any container runtime. Therefore all configuration is handled through environment variables.

ENV variable setup

| Pattern | Description | Sample Value |
| ------- | ----------- | ------------ |
| SOURCE_TYPE | router layer type | google-pubsub |
| SOURCE_EDGE2LOCALSUBSCRIPTION | name of the topic subscription | |
| SOURCE_SERVICEACCOUNT | account as inline json string | |
