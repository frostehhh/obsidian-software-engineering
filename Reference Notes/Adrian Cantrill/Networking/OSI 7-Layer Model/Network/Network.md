---
aliases: [Layer 3]
---
- Gets data from one location to another
- Adds the [[Reference Notes/Adrian Cantrill/Networking/OSI 7-Layer Model/Network/Internet Protocol]] (IP) capability, which is a layer 3 protocol which adds network [[IP Addressing]] and routing to move data between Local Area Networks without direct P2P links
- [[Reference Notes/Adrian Cantrill/Networking/OSI 7-Layer Model/Network/IP Packet]]s are moved step by step from source to destination via intermediate networks. <mark style="background: #FFF3A3A6;">Encapsulated in different frames along the way.</mark>
- Routers (L3) decides, remove frame encapsulation and add new frame encapsulation at every hop
- Adds [[Route Table & Routes]]
- Adds [[Address Resolution Protocol|ARP]]
- Can utilize [[Network Address Translation|NAT]]

### Example

![[OSI-LAYER3-NETWORK-1.png]]
- [[IP Routing Example]]

### Related Topics
[[IP Subnetting]]