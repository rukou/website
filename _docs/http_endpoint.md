---
layout: docs
title: Http Endpoint
category: Edge Layer
order: 700
---

ENV variable setup

| Pattern | Description | Sample Value |
| ------- | ----------- | ------------ |
| ENDPOINTS_{id}_TYPE | endpoint type | http |
| ENDPOINTS_{id}_URL | url | 'http://mbp.fritz.box:8161/api/message/TEST?type=queue' |
| ENDPOINTS_{id}_HEADER_{NR} | http header, {NR} can be arbitrary as long as it is unique | 'Authorization: Basic YWRtaW46YWRtaW4=' |
