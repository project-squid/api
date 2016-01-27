---
title: 'Response status codes'

layout: nil
---

### Success

Successes differ from errors in that their body may not be a simple response object with a code and a message. The headers however are consistent across all calls:

* `GET` return `200 OK` on success,

### Redirect

The API calls that return a random work will return a redirect to a URL
with the random work.

```Status: 303 See Other```
```Location: http://example.endpoint.io/works/28353```

### Error

Error responses are simply returning [standard HTTP error codes](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html) along with some additional information:

* The error code is sent back as a status header,
* The body includes an object describing both the code and message (for debugging and/or display purposes),

For a call with an invalid hash format for instance:

```Status: 400 Bad Request```
```
   hash must be a 256-bit hexadecimal encoded value
```
