---
tags:
  - notes
  - networking
  - backend
  - communication/protocols
Draft: false
"related-reference-note:":
  - "[[TCP]]"
"Parent:":
  - "[[Notes/OSI Model/Transport|OSI Model - Layer 4]]"
"similar:":
  - "[[Notes/User Datagram Protocol|User Datagram Protocol]]"
---

- [[Notes/OSI Model/Transport|OSI Model - Layer 4]]
- Stateful
- Control of communication
- Requires communication/session to be established
	- Establishment of session is layer 5
	- Requires handshake
- Used by HTTP
- Reliable
- TCP Segment
- Address processes in a host via ports
- bi-directional
- file descriptor - contains information regarding connection "ID"
- Utilizes the concept of [[Notes/Multiplexing and Demultiplexing#Multiplexing|Multiplexing]] and [[Notes/Multiplexing and Demultiplexing#Demultiplexing|Demultiplexing]]
	- Client multiplexes multiple connections from different processes into 1 UDP connection. Receivers demultiplexes
- 20 bytes headers **Segment**(max 60 bytes)

# Use Cases
- Database queries
- Requests to update data
- Uploads and downloads of files

# Connection
- Sender sends TCP segments
- Receiver confirms receival of segments
- Segments are sequenced
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

# Anatomy
- Ports - source and destination
- Sequence number
- ACK number
- 9 control bits
	- SYN
	- ACK
	- FIN
	- ...
- Window size - Accepted size by server(?)
- options
- checksum
![[Pasted image 20250321231911.png]]

# Maximum Segment Size
![[Pasted image 20250321231824.png]]

# References
https://en.wikipedia.org/wiki/Transmission_Control_Protocol