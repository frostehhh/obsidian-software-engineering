---
tags:
  - notes
  - networking
  - backend/communication
Draft: false
"Parent:":
  - - Notes/Internet Protocol|Internet Protocol
---
- IP Packet contains importantly the following
	- Header - Max 480 bits
		- Source IP address
		- Destination IP Address

		- Options
		- Total Length - 2 bytes = 16 bits - to indicate total size of IP packet. Size to IP packet is equivalent to 2^16 bits 65536 bits or 65.536 kb. 
		- Version - v4 or v6
		- Protocol - protocol used by the data
		- Fragmentation info
		- ECN
		- Time to Live(TTL) - decrements after each hop
		- IHL - 4 bits - 15(max number that can be indicated by 4 bits) x 32 = 480 bits = max size of header.
	- Data

![[Pasted image 20250317224513.png]]
# References
[[IP-TCP-UDP-TLS+Slides.pdf#page=9]]
https://en.wikipedia.org/wiki/IPv4