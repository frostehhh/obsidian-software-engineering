---
tags:
  - notes
  - networking
  - backend/communication
Draft: false
aliases:
  - HTTP
"related-reference-note:": "[[HTTP 1.1]]"
---

# HTTP/1.0
- Connection is opened and closed for each and every request
	- slow as a result
# HTTP/1.1
- Persistent TCP Connection
	- faster due to less overhead of initializing connection
- Includes pipelining(disabled by default due to flaws)
- Supports proxying and multi-homed websites
	- Multi-homed websites pertain to multiple DNS hostnames pointing to the same IP address
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