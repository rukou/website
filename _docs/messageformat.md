---
layout: docs
title: Message Format
category: router layer
order: 200
---
All Communication between Edge Layer and Local Layer happen throough message based communication.

The following message formats exists:
* http-request
* http-response


## http-request

This message type is used to transport incoming http-requests to an arbitrary endpoint.

### Message Header

| Name | Cardinality | Datatype | Value | Description |
| -  |  :-: | :-: | - | - |
| X-MESSAGE-TYPE | required | string | http-request | type pf the message |
| X-MESSAGE-VERSION | required | string | 2020-05-22 | Version of the message |
| X-REQUEST-ID | required | string | sample: 953bd331-8a3f-41fe-887d-9c819201d32b |
| X-ENDPOINT-TYPE | required | string | supported values are 'echo','http' |
| X-HTTP-METHOD | required | string | sample: 'GET', 'POST', 'DELETE' ... |
| X-HTTP-PATH | required | string | sample: '/order/123' |
| X-CONTENT-ISNULL | optional | string | supported values are 'true','false' |
| X-HTTP-TIMESTAMP | required | string | sample: 2020-05-01T09:12:32Z | received timestamp |
| X-LOCAL2EDGE-DESTINATION | required | string | sample: local2edge | |

### Message Body

The body contains a exact representation of the request body received by the edge layer.s

## http-response

### Message Header

| Name | Cardinality | Datatype | Value | Description |
| -  |  :-: | :-: | - | - |
| X-MESSAGE-TYPE | required | string | http-request | type pf the message |
| X-MESSAGE-VERSION | required | string | 2020-05-22 | Version of the message |
| X-REQUEST-ID | required | string | sample: 953bd331-8a3f-41fe-887d-9c819201d32b |
| X-ENDPOINT-TYPE | required | string | supported values are 'echo','http' |
| X-HTTP-METHOD | required | string | sample: 'GET', 'POST', 'DELETE' ... |
| X-HTTP-PATH | required | string | sample: '/order/123' |
| X-CONTENT-ISNULL | optional | string | supported values are 'true','false' |
| X-HTTP-TIMESTAMP | required | string | sample: 2020-05-01T09:12:32Z | received timestamp |
| X-HTTP-STATUSCODE | required | string | sample: 200 | http status code for the response |

### Message Body
