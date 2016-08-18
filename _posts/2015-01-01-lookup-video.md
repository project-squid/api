---
category: Videorooter API
apipath: '/lookup/video'
title: 'Lookup a video by its calculated hash'
type: 'GET'

layout: nil
---

This is an experimental call to look up a video by its blockhash. The
call conforms to the same specification as ```/lookup/hash```, namely the
[http://docs.cmcatalog.apiary.io/](Elog.io API specification). It allows
you to lookup videos based on an experimental [https://github.com/commonsmachinery/blockhash-rfc](blockhash) algorithm which is implemented in
[https://github.com/jonasob/blockhash](code only).

The maximum hash distance is controlled by the server and cannot be
increased by the client. It may however be decreased.  Currently the
maximum hash distance is 40.


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
