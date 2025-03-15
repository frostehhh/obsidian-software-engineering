---
aliases: [TCP]
---

- for reliability,error correction and ordering of data
- Used by HTTP, HTTPS, SSH, etc.
- connection-oriented protocol
- Segments are another container for data similar to [[Reference Notes/Adrian Cantrill/Networking/OSI 7-Layer Model/Network/IP Packet|packet]]s and [[Frames]], but they are specific to TCP
- [[Segments]] are encapsulated within [[Reference Notes/Adrian Cantrill/Networking/OSI 7-Layer Model/Network/IP Packet]]s

### Example
![[OSI-LAYER4-TRANSORT-3.png]]
- Ephemeral port - a temporarily created port, which is used as a source port in a client server connection. Also called high ports
- Port 443 is a well known server port ([ref](https://sectigostore.com/blog/port-443-everything-you-need-to-know-about-https-443/a))

### Related Topics
[[TCP Connection 3-way Handshake]]
[[Sessions & State - Firewalls]]

### References
https://www.geeksforgeeks.org/services-and-segment-structure-in-tcp/