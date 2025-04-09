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

## If-Modified-Since
## Vary
## Expires
`max-age` in `Cache-Control` header

## Request Collapse

## Common Caching Patterns



# References
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Evolution_of_HTTP#http1.1_%E2%80%93_the_standardized_protocol

# Questions
- What is pipelining?