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
<!--SR:!2025-08-02,32,270-->
+++

What header do you use to prompt if a stale resource has changed?::`If-Modified-Since`[^1]
<!--SR:!2025-11-14,153,310-->

What headers are used for client and server to determine the compression algorithm to use[^2]
?
`Accept-Encoding`(response) and `Content-Encoding`(request)
<!--SR:!2025-09-20,87,290-->
+++

What does a simple authentication flow look like in HTTP?[^3]
?
1. Client sends request to server
2. Server responds with status code `401` `Unauthorized` and sends a header `WWW-Authenticate` or `Proxy-Authenticate` if it's from a proxy server. The header value indicates the method for authorization needed
3. The client can send a request including a header of either `Authorize` or `Proxy-Authorize`, which include the credentials for authorization
	- If successful, server can return status code `200`
	- If unsuccessful, server can send status code `401` `Unauthorized`. To hide the existence of a resource, `404` `Not Found` can also be returned
<!--SR:!2025-06-27,13,270-->
+++

What headers are used for authentication?[^3]
?
`WWW-Authenticate` and `Proxy-Authenticate` by server
`Authorize` and `Proxy-Authorize` by client
<!--SR:!2025-09-23,101,310-->
+++

What are the common authentication schemes[^3]
?
Basic
Bearer
Digest
<!--SR:!2025-10-31,128,298-->
+++

What are the purpose of cookies in HTTP?[^4]
?
Session management
Tracking
User preferences
<!--SR:!2025-10-04,112,298-->
+++

[^1]: [[HTTP Headers]]
[^2]: [[Hypertext Transfer Protocol|HTTP]]
[^3]: [[Authentication]]
[^4]: [[HTTP Cookies]]
