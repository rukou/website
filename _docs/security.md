---
layout: docs
title: Security
category: General
order: 640
---

Since Rukou provides external access to internal systems, we take security very seriouosly.

**The Basics:**

* All communication is encrypted at all time
* All data at rest is encrypted at all time

<br>

### Edge Layer in Detail

All incoming communication is checked against a list of white-listed domains, that the server should accept connections for.

All incoming communication is filtered by an endpoint ruleset before any information is forwarded to the Router Layer.

<br>

### Router Layer in Detail

Since the Router Layer is provided by some publicly available Messaging Service, please refer to the security documentation of the service provider.

<br>

### Local Layer in Detail

The Local Layer only accept incoming communication from Router Layer, there is no other way to transfer messages into the Local Layer.

The configuration for the Local Layer only consists of the connection parameter to the Router Layer. No Enpoint information, like URL, User or Passwords will be persisted in the Local Layer.

The Local Layer can be restricted to only access certain hosts within the intranet zone. This behavior can be set through the container environment and is **not** changeable by the Edge or Router Layer.