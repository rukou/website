---
layout: docs
title: Getting Started
category: general
order: 200
---
Deployments have to be separated into layers. Each layer has their own runtime and deployment instructions.

For a detailed instructions and template head over to our [github repository](https://github.com/rukou).

## Edge Layer

The Edge Layer is provided through a Kubernetes deployment which can be hosted on any Cluster.

## Routing Layer

The Routing Layer is usually implemented by a publicly available messaging provider.
We currently support the following provider for message routing:
 
* Google PubSub
* Azure ServiceBus

For a full routing setup, we need one Destination for Edge-To-Local communication and one Destination for Local-To-Edge comminucation. 

## Local Layer

The Local Layer can be implemented through a Docker image. We provide out-of-box support for the following backend technologies:

* API
* Kafka
* JMS

Other backends can be created with the provided instructions.