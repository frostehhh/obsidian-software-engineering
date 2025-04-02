---
tags:
  - notes
  - backend/communication/protocols
  - networking
Draft: false
aliases:
  - UDP
"related-reference-note:":
  - "[[UDP]]"
"similar:":
  - "[[Notes/Transmission Control Protocol|Transmission Control Protocol]]"
has-questions: true
---

- [[Notes/OSI Model/Transport|Transport]]
- Stateless
- No initial connection needed
- Used by WebRTC
- Better for processes that want more real-time processing of information
- Address processes in a host via ports
- Simple
- Utilizes the concept of [[Notes/Multiplexing and Demultiplexing#Multiplexing|Multiplexing]] and [[Notes/Multiplexing and Demultiplexing#Demultiplexing|Demultiplexing]]
	- Client multiplexes multiple connections from different processes into 1 UDP connection. Receivers demultiplexes
- 8 bytes header
# Examples
- Online games
- Livestreams
- Video calls
# Anatomy
The header simply contains the following
- Source port
- destination port
- length
- checksum

# Pros
- Low latency due to low overhead
- simple
- No need to connection
- stateless
![[Pasted image 20250320011231.png]]
# Cons
- Can be abused by spamming UDP datagrams to a target that they will be forced to process due to the stateless nature of UDP
- No flow control
- No congestion control
![[Pasted image 20250320011242.png]]

# Questions

How does TCP use UDP?
DNS poisoning?