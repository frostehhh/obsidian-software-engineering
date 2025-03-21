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

# How is a connection established?
3-way TCP handshake?
Combination of the following determines a connection:
- Source IP
- Source Port
- Destination IP
- Destination Port
# Questions
What is TCP vs UDP?