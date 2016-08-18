---
category: Videorooter internal API
apipath: '/videorooter/video'
title: 'Submit a video to be processed / looked up'
type: 'POST'

layout: nil
---

This is part of a set of API calls which are specific for the Videorooter
project and used internally by its website. It's possible to use these
calls externally too, but the results may vary and change frequently.

This call sends a file to the Videorooter backend to be queried for in
the database. The results are not immediately returned. Rather, this
call returns a process identifier which is randomly selected. Subsequent
calls shall be made to the `/videorooter/results` method to get the actual
results once processing has completed. This may take several minutes.

If an email address is provided, an email will be generated and sent to
this address once processing has completed.

Here's an example of how you could manually invoke this method:

  $ curl -F "email=youremail" \
         -F "file=@/path/to/file.mp4" \
         http://devc.commonsmachinery.se:8080/videorooter/video

### Request

* **`:email`** (string, optional) is the email address of the user
* **`:file`** (file) is the contents of the file to query for

### Response

Returns a process identifier which can be used for subsequent calls.

```Status: 200 OK```
```{
      "process_id": "c82b103606ba83a3c75819a6301a7417"
}
```

For errors responses, see the [response status codes documentation](#response-status-codes).
