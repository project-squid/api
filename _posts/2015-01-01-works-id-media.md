---
category: Elog.io compatibility
apipath: '/works/<id>/media'
title: 'Get the media associated with a work'
type: 'GET'

layout: nil
---

This is a compatibility call conforming to the
[http://docs.cmcatalog.apiary.io/](Elog.io API specification). It queries
the database for a particular work by its identifier and returns the media
(source images) associated with it.

### Response

Sends back information with a location annotation giving the link to
the source work.

```Status: 200 OK```
```{ "annotations":
       [{
           "property":
               {
                  "propertyName": "locator",
                  "locatorLink": "https://example.image.io/image.png"
               }
       }],
     "href": "http://example.endpoint.io/works/3948734/media",
     "id": 3948734
   }
```

For errors responses, see the [response status codes documentation](#response-status-codes).
