---
layout: docs
title: Configuration
category: Local Layer
order: 200
---
The local layer is build for any container runtime. Therefore all configuration is handled through environment variables.

#### ENV variable setup

| Pattern | Description | Sample Value |
| ------- | ----------- | ------------ |
| SOURCE_TYPE | router layer type | google-pubsub |
| SOURCE_EDGE2LOCALSUBSCRIPTION | name of the topic subscription | |
| SOURCE_SERVICEACCOUNT | account as inline json string | |

<br>
#### Sample Config for Google PubSub Routing

| Name | Value |
| ------- | ----------- |
| SOURCE_TYPE | google-pubsub |
| SOURCE_EDGE2LOCALSUBSCRIPTION |  |
| SOURCE_SERVICEACCOUNT | { "hallo": "welt"} |

<br>
#### Sample Config for Azure Eventhub Routing

| Name | Value |
| ------- | ----------- |
| SOURCE_TYPE | azure-eventhub |
| SOURCE_EDGE2LOCAL | {endpointurl} |

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>