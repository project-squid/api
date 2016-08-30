---
category: Videorooter internal API
apipath: '/videorooter/works/&lt;id>/media'
title: 'Get the media associated with a work'
type: 'GET'

layout: nil
---

This call queries
the database for a particular work by its identifier and returns the media
(source images) associated with it.

### Response

Sends back information with a location annotation giving the link to
the source work.

```Status: 200 OK```
```{ "locator": "https://example.image.io/image.png",
     "href": "http://example.endpoint.io/works/3948734/media",
     "id": 3948734,
     "identifiers": [
        "http://sample/hash/2/38763q4420834",
        "http://sample/hash/1/23o34934",
     ]
   }
```

For errors responses, see the [response status codes documentation](#response-status-codes).
