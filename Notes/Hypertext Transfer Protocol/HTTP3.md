---
tags:
  - notes
  - backend/communication
  - backend/networking
Draft: false
"Parent:": "[[Hypertext Transfer Protocol]]"
"prev-version:": "[[Notes/Hypertext Transfer Protocol/HTTP2|HTTP2]]"
---

- HTTP/3 is an improvement over HTTP/2.
- uses Quick UDP Internet Connection(QUIC) protocol to establish TLS and connection in one handshake 

# Example
![[Pasted image 20250322221133.png]]
# Problem with HTTP/2
Head-of-line blocking and reliance of in-order segments to be sent due to TCP being used as a protocol.

# Pros
- Segments can be sent out of order via streams
	- As a result, better for lossy connections
- Congestion Control at stream level
- Connection migration via connectionID

> [!warning] 
> HTTP/2 over QUIC is not viable due to the header compression algorithm. The HPAC algorithm depends on TLS sending segments in order 

# Cons
- Requires more CPU resources
- UDP could be blocked
- IP Fragmentation could break this

# HTTPS with QUIC
![[Pasted image 20250323171913.png]]
HTTPS is implemented as part of the connection establishment

## With 0RTT
![[Pasted image 20250323173617.png]]