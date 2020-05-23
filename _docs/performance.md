---
layout: docs
title: Performance
category: general
order: 500
---

We regularily perform performance test and will publish our results here.

## Test Scenario

Last Update: 2020-05-23

Tested Version: 1.0

* Edge Layer is GKE in europe-west4.
* Router Layer is Google PubSub.
* Local Layer is Macbook (also in Germany).

## Performance

ApacheBench excerpt:

    Concurrency Level:      10
    Time taken for tests:   5.915 seconds
    Complete requests:      500
    Failed requests:        0
    Total transferred:      119500 bytes
    Total body sent:        114500
    HTML transferred:       49000 bytes
    Requests per second:    84.52 [#/sec] (mean)
    Time per request:       118.309 [ms] (mean)
    Time per request:       11.831 [ms] (mean, across all concurrent requests)
    Transfer rate:          19.73 [Kbytes/sec] received
                            18.90 kb/s sent
                            38.63 kb/s total

    Connection Times (ms)
                min  mean[+/-sd] median   max
    Connect:       42   49   4.9     48      79
    Processing:    56   66   8.1     64     136
    Waiting:       55   65   7.9     63     136
    Total:         99  115  10.2    113     191

    Percentage of the requests served within a certain time (ms)
    50%    113
    66%    116
    75%    119
    80%    120
    90%    125
    95%    132
    98%    148
    99%    167
    100%    191 (longest request)