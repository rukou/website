---
layout: docs
title: Configuration
category: Local Layer
order: 200
---
The local layer is build for any container runtime. Therefore all configuration is handled through environment variables.

ENV variable setup

| Pattern | Description | Sample Value |
| ------- | ----------- | ------------ |
| SOURCE_TYPE | router layer type | google-pubsub |
| SOURCE_{property} | technology specific property | |

<br>

### Google PubSub Routing

| Name | Value |
| ------- | ----------- |
| SOURCE_TYPE | google-pubsub |
| SOURCE_PUBSUB_SUBSCRIPTION | full name of the subscription |
| SOURCE_PUBSUB_SERVICEACCOUNT | JSON value of the service account |

<br>

**Sample configuration**

    SOURCE_TYPE: google-pubsub
    SOURCE_PUBSUB_SUBSCRIPTION: projects/rukou/subscriptions/edge2local-subscription
    SOURCE_PUBSUB_SERVICEACCOUNT: {...}

<br>

### Azure Eventhub Routing

| Name | Value |
| ------- | ----------- |
| SOURCE_TYPE | azure-eventhub |
| SOURCE_EVENTHUB_URL | url of the eventhub (including access key) |

<br>

**Sample configuration**

    SOURCE_TYPE: azure-eventhub
    SOURCE_EVENTHUB_URL: Endpoint=sb://rukou.servicebus.windows.net/Endpoint=sb://rukou.servicebus.windows.net/;SharedAccessKeyName=key;SharedAccessKey=9xabc...

<br>
<br>

For more sample, please check out our sample section managed through the following repo.

[https://github.com/rukou/deployment-samples/tree/master/local_layer](https://github.com/rukou/deployment-samples/tree/master/local_layer)

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>