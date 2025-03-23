---
tags:
  - notes
  - backend/networking
  - backend/communication
Draft: true
aliases: NAT
---

# Network Address Translation
A protocol for converting private IP address + port to external IP + port through a gateway.

# Types
## One to One NAT
A sender's private IP + Port is converted to public IP + Port.
The receiver can communicate back with no restrictions

# Address Restricted NAT
A client can receive requests only from IP Addresses it knows or has communicated with before

# Port Restricted NAT
A client can receive requests only from IP Address + Port combinations it knows or has communicated with before

# Symmetric NAT