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

# Compression
- Decreasing data size for more efficient data transport
- Uses `Accept-Encoding` request header to communicate supported encoding methods
## Levels to apply
1. Data level
2. HTTP Level ([[Notes/OSI Model/Application|OSI Model - Layer 7]])
3. TCP Level ([[Notes/OSI Model/Transport|OSI Model - Layer 4]])
## Compression Libraries
- gzip - most common
- br - more recent

# References
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Evolution_of_HTTP#http1.1_%E2%80%93_the_standardized_protocol

# Questions
- What is pipelining?