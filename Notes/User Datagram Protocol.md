---
tags:
  - notes
  - backend/communication
  - backend/networking
Draft: true
aliases: UDP
related-reference-note:: [[UDP]]
---

- [[layer 4 protocol]]
- Stateless
- No initial connection needed
- Used by WebRTC
- Better for processes that want more real-time processing of information
- Address processes in a host via ports
- 8 bytes header
- Simple
- Utilizes the concept of [[Notes/Multiplexing and Demultiplexing#Multiplexing|Multiplexing]] and [[Notes/Multiplexing and Demultiplexing#Demultiplexing|Demultiplexing]]
	- Client multiplexes multiple connections from different processes into 1 UDP connection. Receivers demultiplexes
# Examples
- Online games
- Livestreams
- Video calls
# Anatomy

# Pros
# Cons

# Questions

How does TCP use UDP?
DNS poisoning?