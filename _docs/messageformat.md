---
layout: docs
title: Message Format
category: Router Layer
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
| X-MESSAGE-TYPE | required | string | http-request | type of the message |
| X-MESSAGE-VERSION | required | string | 2020-05-22 | Version of the message |
| X-REQUEST-ID | required | string | sample: 953bd331-8a3f-41fe-887d-9c819201d32b |
| X-ENDPOINT-TYPE | required | string | supported values are 'echo','http' |
| X-ENDPOINT-ID | required |string | sample: 'ENDPOINT1' |
| X-HTTP-METHOD | required | string | sample: 'GET', 'POST', 'DELETE' ... |
| X-HTTP-PATH | required | string | sample: '/order/123' |
| X-HTTP-QUERY | optional | string | sample: 'param1=value1&param2=value2' |
| X-HTTP-HOST | required | string | sample: 'api.domain.tld' | hostname of the request |
| X-HTTP-TIMESTAMP | required | string | sample: 2020-05-01T09:12:32Z | received timestamp |
| X-LOCAL2EDGE-DESTINATION | required | string | sample: local2edge | |

### Message Body

The body contains a exact representation of the request body received by the edge layer.

## http-response

### Message Header

| Name | Cardinality | Datatype | Value | Description |
| -  |  :-: | :-: | - | - |
| X-MESSAGE-TYPE | required | string | http-request | type pf the message |
| X-MESSAGE-VERSION | required | string | 2020-05-22 | Version of the message |
| X-REQUEST-ID | required | string | sample: 953bd331-8a3f-41fe-887d-9c819201d32b |
| X-HTTP-STATUSCODE | required | string | sample: 200 | http status code for the response |
| X-CONTENT-ISNULL | optional | string | supported values are 'true','false' |
| X-HTTP-TIMESTAMP | optional | string | sample: 2020-05-01T09:12:32Z | received timestamp |

### Message Body

The body contains a exact representation of the response body received by the local layer.

<style>
td, th {
    border: 1px solid var(--secondary);
    padding: 0.5em;
}
</style>
