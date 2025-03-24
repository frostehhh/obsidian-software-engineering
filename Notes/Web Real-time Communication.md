---
tags:
  - notes
  - backend/communication
  - networking
Draft: false
related-reference-note:: [[WebRTC]]
aliases: WebRTC
---

# WebRTC
- protocol helps in finding best route for communication. Shortest path through the internet
# Usecases
- Peer-to-peer connection
- Video call
- Voice call
- Streaming
- Online Gaming

![[Notes/Network Address Translation#Network Address Translation|Network Address Translation]]

# Session Traversal Utilities For NAT(STUN)
- Server
- uses ICE
- Helps peers connect to each other

# Traversal Using Relays around NAT(TURN)
- TURN Server
- Solution for clients/servers that use symmetric NAT

# Interactive Connectivity Establishment(ICE)
- Explores possible connections to find the best communication path
- Framework

# Session Description Protocol(SDP)
- It is an "Offer" a client sends to another client it wants to connect to
- Contains information gathered from ICE. Connection candidates
- Contains other relevant information

# SDP Signaling
- Responsible for passing SDPs between 2 clients
- Responsibility can be passed to a server

# How WebRTC and underlying components work with each other to establish a connection between 2 peers

![[Web Real-time Communication 2025-03-23 15.07.41.excalidraw]]

# References
https://www.youtube.com/watch?v=WmR9IMUD_CY