---
category: Squid
path: '/lookup/blockhash'
title: 'Lookup a work by its calculated hash'
type: 'GET'

layout: nil
---

This is a compatibility call conforming to the
[http://docs.cmcatalog.apiary.io/](Elog.io API specification). It allows
you to lookup images based on the [https://github.com/commonsmachinery/blockhash-rfc](blockhash perceptual hashing method).

The maximum hash distance is controlled by the server and cannot be
increased by the client. It may however be decreased.  Currently the
maximum hash distance is 10.


### Request

* **`:hash`** (string) is the calculated hash to lookup
* **`:distance`** (number, optional) is the maximum hash distance (10 by
default)

### Response

Sends back a collection of matching works. The reference returned is a
URI which can be used to further query the resource for additional
information about the work.

```Status: 200 OK```
```[
    {
        "href": "http://example.endpoint.io/works/5396e592d7d163613d7321ee"
        "distance": 2
    },
    {
        "href": "http://example.endpoint.io/works/d7321ee5396e592d7d163613"
        "distance": 8
    }
]```

For errors responses, see the [response status codes documentation](#response-status-codes).
