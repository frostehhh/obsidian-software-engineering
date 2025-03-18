---
tags:
  - backend/networking
  - notes
  - backend/communication
Draft: false
"Parent:":
  - - Notes/OSI Model/Network|Network
related-reference-note:: [[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Backend Engineering/Section 3 - Protocls/Internet Protocol|Internet Protocol]]
---
# IP Address
- Layer 3 property
- Can be set automatically or statically
- Contains network and host portion
# Network
- In an IPv4 address, the format is like x.x.x.x where x is any number from 0 - 255. Dotted decimal notation
- Given an IP address 192.168.1.0/24. This is a subnet
	- /24 is the subnet mask. This describes the network portion of an ip address
	- /24 is equivalent to 255.255.255.0
	- The last part is the hosts part.
	- A subnet is a subnetwork. A network within a network.
# Default Gateway
- This is an IP address allocated to a router responsible for communicating with other networks. Hosts in a subnet must route their requests to this default gateway to communication with other subnets/networks.
- Can be described as a coordinator to other networks



# References
[[IP-TCP-UDP-TLS+Slides.pdf]]