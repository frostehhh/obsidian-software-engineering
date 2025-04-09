---
tags:
  - notes
  - networking
  - backend/communication/protocols
Draft: false
aliases:
  - HTTP
"related-reference-note:": 
 - "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Backend Engineering/Section 3 - Protocols/HTTP 1.1]]"
---
- Stateless
- A communication protocol primarily for data exchange
# HTTP/1.0
- Connection is opened and closed for each and every request
	- slow as a result

![[Notes/Hypertext Transfer Protocol/HTTP 1.1|HTTP 1.1]]
## Request Structure
- Method
- Path 
- Protocol
- Headers
- Body
![[HTTP Request Structure.png]]
## Response Structure
- Protocol
- Code
- Code Text
- Headers
- Body
![[Pasted image 20250322024120.png]]

HTTP Smuggling?

# HTTP/2
- Applies [[Notes/Multiplexing and Demultiplexing#Multiplexing|Multiplexing and Demultiplexing]]
![[HTTP2.png]]
See [[Notes/Hypertext Transfer Protocol/HTTP2|HTTP2]]
# HTTP/3
- All features of [[#HTTP/2]]
- Uses [[QUIC]](UDP with congestion control) instead of TCP
- Without HOL(head-of-line)

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

[^1]

# References
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview#see_also

[^1]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Compression
