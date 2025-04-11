---
tags:
  - flashcards
  - communication/protocols/http
  - backend
Draft: true
---


What HTTP header requires that a resource be validated before reuse?::no-cache[^1]

What is ETAG for and how do you use it?[^1]
?
ETAG is a response header and a unique identifier for a resource. It is paired with the `If-None-Match` request header.
+++

What header do you use to prompt if a stale resource has changed?::`If-Modified-Since`[^1]

What headers are used for client and server to determine the compression algorithm to use[^2]
?
`Accept-Encoding`(response) and `Content-Encoding`(request)
+++

[^1]: [[HTTP Headers]]

[^2]: [[Hypertext Transfer Protocol|HTTP]]
