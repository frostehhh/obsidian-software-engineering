---
aliases:
  - CIDR
tags:
  - networking
  - notes
Friend:: 
  - "[[Notes/Internet Protocol|Internet Protocol]]"
---

# What is Classless Inter-domain Routing
- A method for dividing a network into subnets using Variable-length subnet masking


- CIDR Block
- CIDR Notation

# CIDR Block
A collection of IP Address that share the same network bits

# CIDR Notation
- Consists of an IP Address and the subnet/network mask(used interchangeably)
- Example: `192.1.1.0/23`
	- IP Address is `192.1.1.0`
	- Subnet mask is `/23`

classful IP Addressing?
Class A - 8 network bits
Class B - 16 network bits
Class C - 24 network bits

Limitations of Classful IP Addressing
- Fixed network sizes and results to wastage of IP Addresses
- 