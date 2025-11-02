---
tags:
  - notes
  - backend
  - networking/communication/protocols/http
  - networking
Draft: false
"Parent:": "[[Hypertext Transfer Protocol]]"
"prev-version:": 
"next-version:": "[[Notes/Hypertext Transfer Protocol/HTTP3|HTTP3]]"
---

# HTTP2
- Not an upgrade in a sense that 1.1 -> 2 is a must do
- Primary motivation for HTTP/2 is for when a client needs many multiple requests to send to a server
- Multiplexes connections
- Based on the SPDY protocol
- Compressed headers by default
- Transmits binary data instead of text([[Notes/Hypertext Transfer Protocol/HTTP 1.1|HTTP 1.1]])


# Diagram
![[Pasted image 20250322175949.png]]
# Diagram with Push(deprecated)
![[Pasted image 20250322180015.png]]
# Pros
- Multiplexing multiple requests into one connection. Each request is identified via a stream-id
- Fast throughput of data traveling from client to server
- Server push available
- Secure by default
	- On its own, it is not secure. However, browser implementations require usage of HTTP/2 over [[Notes/Transport Layer Security/Transport Layer Security|TLS]][^1]
- Compression(headers and data)
	- HPACK for header compression[^2]
# Cons
- TCP Head of line blocking - succeeding segments are ignored by server when there are missing preceding TCP segments
- More resources required by server to process multiplexed connection. There is overhead of processing what stream a request is for
- Server push not picked up due to issues
# See Also
https://kinsta.com/learn/what-is-http2/#:~:text=HTTP%2F2%20implementation%20addresses%20these,in%20previous%20client%2Dserver%20requests.

[^1]: https://en.wikipedia.org/wiki/HTTP/2#:~:text=Although%20the%20standard%20itself%20does,IE%2C%20Edge)%20have%20stated%20that

[^2]: https://kinsta.com/learn/what-is-http2/#:~:text=HTTP%2F2%20implementation%20addresses%20these,in%20previous%20client%2Dserver%20requests.
