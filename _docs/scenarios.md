---
layout: docs
title: Deployment Scenarios
category: General
order: 400
---

API routing can be useful in a number of scenarios. We here present a couple scenarios which can be covered through rukou.

## Expose internal application publically

![scenario1](/assets/rukou-scenario1.png)

* business application located in intranet
* expose public endpoint
* route through established cloud layer for secure connectivity

## Multiregional Edge Layer

![scenario2](/assets/rukou-scenario2.png)

* provide endpoints in multiple regions
* segment backend depending on latency needs

## Regional applications

![scenario3](/assets/rukou-scenario3.png)

* business application are deployed into regional setups
* single endpoint
* header based routing into region

## Shared nothing architectures

![scenario4](/assets/rukou-scenario4.png)

* backends are split by functional business service
* backend do not share resources
* single endpoint for service federation


<style>
    @media only screen and (max-width: 617px) {
  img.fill-screen {
    width: 100%
  }
}
