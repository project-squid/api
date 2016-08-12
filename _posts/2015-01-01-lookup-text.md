---
category: Videorooter API
path: '/lookup/text'
title: 'Lookup a work by full text search of key fields'
type: 'GET'

layout: nil
---

This is an experimental call to look up a video by a full text search
of title, description and credit. The call is so far using a natural
language query, meaning that it interprets all fields as natural
language fields and tries to do a best effort matching.

Commonly occuring words like "and", "or", "the", "there", and so on
may be ignored, but more specific words like "tripod" or individual
names will be acted upon.

### Request

* **`:q`** (string) is the search string

### Response

Sends back a collection of matching works. The reference returned is a
URI which can be used to further query the resource for additional
information about the work.

```Status: 200 OK```
```[
    {
        "href": "http://example.endpoint.io/works/5396e592d7d163613d7321ee"
    },
    {
        "href": "http://example.endpoint.io/works/d7321ee5396e592d7d163613"
    }
]```

For errors responses, see the [response status codes documentation](#response-status-codes).
