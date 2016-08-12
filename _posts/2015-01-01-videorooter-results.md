---
category: Videorooter internal API
path: '/videorooter/results/<process_id>'
title: 'Gets information about a previous search'
type: 'GET'

layout: nil
---

This is part of a set of API calls which are specific for the Videorooter
project and used internally by its website. It's possible to use these
calls externally too, but the results may vary and change frequently.

This call inquires about the status of a previous search which has been
made. It returns either a status code of `202` if the search has not
yet been completed, or a list of results.

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
