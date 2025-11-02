---
tags:
  - notes
  - networking/communication/protocols/http
aliases:
  - CORS
Draft: true
---

- Cross-origin resource sharing(CORS) describes the sharing of resources between different origins

> [!example]
> Origin 1: http://domain-a.com
> Origin 2: http://domain-b.com
> 
> A web server hosted on http://domain-a.com sends a request to http://domain-b.com

# Purpose
- Access control for requests that a server can receive based on the origin
# Preflight Request
- A request sent with the HTTP OPTIONS method
- Asks if there is permission to send a request with a given set of header values
	- Origin
	- Methods
	- Content-Type
	- etc.
- Sent prior to actual request if it is NOT a [simple request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CORS#simple_requests)
	- Main differentiator -> GET, HEAD, POST can be simple, but not all
# CORS Headers
- Access-Control-Allow-Methods
- Access-Control-Allow-Origin
- Access-Control-Allow-Headers
- Access-Control-Max-Age
# Questions
- What is a preflight request?
- When are preflight requests sent?

# References
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CORS