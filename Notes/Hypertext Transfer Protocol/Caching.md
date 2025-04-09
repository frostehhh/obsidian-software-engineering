---
tags:
  - backend/communication/protocols
  - notes
"Parent:":
  - "[[Hypertext Transfer Protocol|HTTP]]"
aliases:
  - HTTP Caching
---

# Caching

- Storing of data in alternative locations typically outside of the main data storage
- used for preventing additional resource usage and consequently, optimizing resources
- `Cache-Control` header[^2]

## Heuristic Caching
Caching that is performed when no caching is suggested from the  `Cache-Control` header
## Types
### Private Cache
Client-only cache
### Shared Cache
Cache storage from multiple different sources

#### Proxy Cache
- Cache stored in proxies
- Clients and servers tend to have no control over these
- Nowadays, commonly not used anymore
#### Managed Cache
- Handled by services

## Expires
- `max-age` in `Cache-Control` header
	- indicates client when data is fresh or stale
	- Client computes age by `max-age - current_time()`
Related to `If-Modified-Since`
## Validation
### If-Modified-Since
- Request header
- If resource age is expired, pass `If-Modified-Since` header to check if resource has been updated
### If-None-Match
- "if ID value provided doesn't match with any existing ID value, proceed with request. Otherwise, return 304 Not modified"
## ETAG
- ETAG is used to uniquely identify a resource
	- Response header
## Vary[^1]
- Response header
- Indicates headers related to caching
- Example: `Vary: Accept-Language`


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
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Caching

[^1]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Vary

[^2]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cache-Control
