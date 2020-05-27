---
layout: docs
title: Configuration
category: Local Layer
order: 200
---
The local layer is build for any container runtime. Therefore all configuration is handled through environment variables.

ENV variable setup

| Pattern | Cardinality | Description | Sample Value |
| ------- | ----------- | ----------- | ------------ |
| SOURCE_TYPE | required | router layer type | google-pubsub |
| SOURCE_{property} | required | technology specific property | |
| SOURCE_TRUSTEDHOSTS | optional | provide a list of hosts (comma separated) the Local Layer is allowed to access, empty means no restrictions. | api.domain.tld,api-test.domain.tld

<br>

### Google PubSub Routing

| Name | Cardinality | Value |
| ---- | ----------- | ----- |
| SOURCE_TYPE | required | google-pubsub |
| SOURCE_PUBSUB_SUBSCRIPTION | required | full name of the subscription |
| SOURCE_PUBSUB_SERVICEACCOUNT | required | JSON value of the service account |

<br>

**Sample configuration**

    SOURCE_TYPE: google-pubsub
    SOURCE_PUBSUB_SUBSCRIPTION: projects/rukou/subscriptions/edge2local-subscription
    SOURCE_PUBSUB_SERVICEACCOUNT: {...}

<br>

### Azure Eventhub Routing

| Name | Cardinality | Value |
| ---- | ----------- | ----- |
| SOURCE_TYPE | required | azure-eventhub |
| SOURCE_EVENTHUB_URL | required | url of the eventhub (including access key) |

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