---
category: Videorooter internal API
apipath: '/videorooter/works/&lt;id>'
title: 'Get the metadata associated with a work'
type: 'GET'

layout: nil
---

This call queries
the database for a particular work by its identifier and returns the known
metadata about the work. This information is in a simplified
[W3C Ontology for media resources](http://www.w3.org/TR/mediaont-10/) format and uses similar naming but different style of presenting the information.

### Response

Sends back information with annotations.

```Status: 200 OK```
```
{
   "description" : "Script logo for athletics at Elon University.",
   "id" : 6968,
   "annotations" : {
         "title" : "Elon Phoenix wordmark",
         "identifier" : "https://commons.wikimedia.org/wiki/File:Elon Phoenix wordmark.png",
         "locator" : "https://upload.wikimedia.org/wikipedia/commons/3/31/Elon_Phoenix_wordmark.png",
         "policy" : "http://creativecommons.org/by-sa/3.0",
         "collection" : "http://commons.wikimedia.org"
         "creator" : "Elon University Athletics",
   }
   "href" : "http://devc.commonsmachinery.se:8080/videorooter/works/6968",
   "media" : [
      {
         "id" : 6968,
         "href" : "http://devc.commonsmachinery.se:8080/videorooter/works/6968/media"
      }
:
   ]
}
```

For errors responses, see the [response status codes documentation](#response-status-codes).
