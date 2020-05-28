---
layout: docs
title: Reference Architecture
category: General
order: 500
---
<style>
    @media only screen and (max-width: 617px) {
  img.fill-screen {
    width: 100%
  }
}
</style>
<div class="container text-center">
<img class="fill-screen" src="/assets/reference.png">
</div>

Our current reference architecture is build from the following components.

#### Edge Layer

Based on the GCP Service catalog:

* External Load-Balancer (for hsoting globally available SSL endpoints)
* Regional GKE (on cluster per required region)

#### Router Layer

* Google PubSub

#### Local Layer

The Local Layer has a very minimal footprint and can be hoosted by various technologies.

* Container Runtime, like Docker, Minikube etc.