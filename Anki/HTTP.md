---
tags:
  - flashcards/http
  - communication/protocols/http
  - backend
Draft: false
---


What HTTP header requires that a resource be validated before reuse?::no-cache[^1]
<!--SR:!2025-07-10,64,310-->

What is ETAG for and how do you use it?[^1]
?
ETAG is a response header and a unique identifier for a resource. It is paired with the `If-None-Match` request header.
<!--SR:!2025-05-14,7,270-->
+++

What header do you use to prompt if a stale resource has changed?::`If-Modified-Since`[^1]
<!--SR:!2025-06-14,38,290-->

What headers are used for client and server to determine the compression algorithm to use[^2]
?
`Accept-Encoding`(response) and `Content-Encoding`(request)
<!--SR:!2025-05-15,8,270-->
+++

What does a simple authentication flow look like in HTTP?[^3]
?
See [[Authentication]]
<!--SR:!2025-06-02,26,290-->
+++

What headers are used for authentication?[^3]
?
`WWW-Authenticate` and `Proxy-Authenticate` by server
`Authorize` and `Proxy-Authorize` by client
<!--SR:!2025-06-01,25,290-->
+++

What are the common authentication schemes[^3]
?
Basic
Bearer
Digest
<!--SR:!2025-06-19,43,298-->
+++

What are the purpose of cookies in HTTP?[^4]
?
Session management
Tracking
User preferences
<!--SR:!2025-06-05,29,278-->
+++

[^1]: [[HTTP Headers]]
[^2]: [[Hypertext Transfer Protocol|HTTP]]
[^3]: [[Authentication]]
[^4]: [[HTTP Cookies]]
