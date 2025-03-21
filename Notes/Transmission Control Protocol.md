---
tags:
  - notes
  - backend/networking
  - backend/communication
Draft: true
related-reference-note:: [[TCP]]
Parent:: [[Notes/OSI Model/Transport|OSI Model - Layer 4]]
similar:: [[Notes/User Datagram Protocol|User Datagram Protocol]]
---

- layer 4 Protocol
- Control of communication
- Requires communication/session to be established
	- Establishment of session is layer 5
- Stateful
- Used by HTTP
- Reliable
- TCP Segment
- bi-directional
- file descriptor - contains information regarding connection "ID"

# Use Cases
- Database queries
- Requests to update data
- Uploads and downloads of files

# Connection
- Sender sends TCP segments
- Receiver confirms receival of segments
- If there are missing segments, sender retransmits them

# How is a connection established?
3-way TCP handshake
![[Transmission Control Protocol 3-way handshake.excalidraw]]
Combination of the following determines a connection:
- Source IP
- Source Port
- Destination IP
- Destination Port

# During a connection
- Sender can send multiple segments at a time.
- Receiver will acknowledge the received segments and indicate the latest segment received where all previous segments are successfully received.
![[Pasted image 20250321185637.png]]
# Closing a connection
![[Transmission Control Protocol 2025-03-21 18.44.11.excalidraw]]

# Questions
What is TCP vs UDP?