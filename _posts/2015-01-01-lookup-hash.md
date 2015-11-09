---
category: Squid
path: '/lookup/hash'
title: 'Lookup a work by its calculated hash'
type: 'GET'

layout: nil
---

Lookup works based on one of several perceptual hashing methods used
to calculate the fingerprint of a work. Please note that not all works 
support the same hash (videos would use video hashes, and images a
blockhash variation, for instance), and as such, searching for a hash
will only return the works that have been hashed with that specific
hash method.

The maximum hash distance is controlled by the catalog and cannot be
increased by the client. It may, however, be decreased. Decreasing the
maximum hash distance will in most cases result in fewer but more
accurate matches.

Pagination is supported by returning a `Link` header with links
according to http://tools.ietf.org/html/rfc5005


### Request

* **`:hash`** (string) is the calculated hash to lookup
* **`:method`** (string) is the method to be used (see the [methods
documentation](#methods) for information
* **`:distance`** (number, optional) is the maximum hash distance (10 by
default)
* **`:page`** (number, optional) is the page to start showing (first
page has index 1)
* **`:per_page`** (number, optional) page should contain these many
records. Default and max values are system-dependent.

### Response

Sends back a collection of matching works. The reference returned us a
URI with an indication of the api that can be used to further query
the resource for additional information about the work. A client may
implement all or some of the [registered APIs](#apis).

```Status: 200 OK```
```[
    {
        "href": "https://catalog.elog.io/works/5396e592d7d163613d7321ee",
        "api": "http://elog.io/",
        "distance": 3
    },
    {
        "href": "https://catalog.elog.io/works/d7321ee5396e592d7d163613",
        "api": "http://elog.io/",
        "distance": 8
    }
]```

For errors responses, see the [response status codes documentation](#response-status-codes).
