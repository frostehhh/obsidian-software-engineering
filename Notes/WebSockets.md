---
tags:
  - notes
  - backend
  - communication/protocols
  - networking
Draft: false
"related-reference-note:":
  - - Reference Notes/Hussein Nasser/Udemy - Fundamentals of Backend Engineering/Section 3 - Protocols/WebSockets|WebSockets
---

- Persistent TCP Connection
- Full-duplex/bi-directional

# Pros
- Realtime
- HTTP Compatible
- Firewall friendly
# Cons
- stateful
- Tricky with proxying
- Tricky with L7 load balancing
# Usecases
- Chatting
- live feed
- notifications

# Request and Response structure
![[WebSocket - Client Server RequestResponse.png]]
# Diagram
![[WebSocket.png]]
# Handshake
![[WebSocket Handshake.png]]
# Related
[[Notes/Push|Push]] - Can refer to this for other details