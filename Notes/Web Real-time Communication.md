---
tags:
  - notes
  - backend/communication
  - backend/networking
Draft: true
related-reference-note:: [[WebRTC]]
aliases: WebRTC
---

# WebRTC
- protocol helps in finding best route for communication. Shortest path through the internet

![[Notes/Network Address Translation#Network Address Translation|Network Address Translation]]

## Types
- One to One NAT
- Address Restricted NAT
- Port Restricted NAT
- Symmetric NAT


STUN(Session Traversal Utilities for NAT)
- Server
- uses ICE?
- Helps peers

TURN(Traversal Using Relays around NAT)
- TURN Server
- Solution for clients/servers that use symmetric NAT

ICE(Interactive Connectivity Establishment)
- Explores possible connections?
- To find the best communication path
- Framework

SDP(Session Description Protocol)
- Offer a client sends to another client it wants to connect to
- Contains information gathered from ICE. Connection candidates

SDP Signaling
- Responsible for passing SDPs
- Responsibility can be passed to a server

# How WebRTC and underlying components work with each other to establish a connection between 2 peers

![[Web Real-time Communication 2025-03-23 15.07.41.excalidraw]]

# References
https://www.youtube.com/watch?v=WmR9IMUD_CY