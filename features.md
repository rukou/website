---
layout: default
title: features
---
### General Features

* Expose Endpoints for API traffic
* Multiple Stages with a single instance
* Backend Routing based on header values (like Host, Path, Method)
* Container-based runtime (Kubernetes deployment recommended)
* Decoupled Backend through Messaging infrastructure


### Edge Layer

* Handle mutiple domains with a single endpoint
* Stateless Engine
* Configuration managed through container native means

### Router Layer

The router layer can be provided through different technologies. Those also bring their own set of functionality.

##### Based on Google PubSub

* multi-region topics
* message sizes of up to 10MB
* zero cost for idle

##### Based on Azure EventHub

* message sizes of up to 1MB (for standard configurations
* message stream can be replicated into kafka-stream

### Local Layer

* Container based Deployment
* Stateless Engine
* Endpoint protocols supported
  * HTTP
  * JMS