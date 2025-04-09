---
tags:
  - scratchpads
Draft: true
has-questions:
---

pipelining
server collocation

# Commonly used headers
## Request Headers
Accept
Accept-Language
Accept-Encoding
Referer
User-Agent
Host

## Response Headers
Connection
Content-Encoding
Content-Type - bytes
Date
Etag
Keep-Alive
Last-Modified
Server
Transfer-Encoding
Vary

# Representation Header
# Methods

# HTTP2 Pseudo-headers

# Caching

- Storing of data in alternative locations typically outside of the main data storage
- used for preventing additional resource usage and consequently, optimizing resources
- `Cache-Control` header
## Types
### Private Cache
Client-only cache
### Shared Cache
Cache storage from multiple different clients
#### Proxy Cache
Cache stored 
#### Managed Cache
- Handled by services

## Validation
## ETAG and If-None-Match
- ETAG is used to uniquely identify a resource
	- Response header
- If-None-Match - "if ID value provided doesn't match with any existing ID value, proceed with request. Otherwise, return 304 Not modified"

## If-Modified-Since
- Request header
- If resource age is expired, pass `If-Modified-Since` header to check if resource has been updated
## Vary
## Expires
`max-age` in `Cache-Control` header
Related to `If-Modified-Since`

## Request Collapse
Scenario when multiple different clients pass the same request to a server, and then

## Common Caching Patterns

### Default
By default no caching for resources
### Cache Busting
- Rely on resource path for caching
- Good for immutable resources - scripts
- For script updates, include version as part of path/filename

# References
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Evolution_of_HTTP#http1.1_%E2%80%93_the_standardized_protocol

# Questions
- What is pipelining?