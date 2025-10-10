---
tags:
  - networking
  - notes
Friend:: 
  - "[[Variable-Length Subnet Masking]]"
  - "[[Classless Inter-domain Routing]]"
Parent:: 
  - "[[Notes/Internet Protocol|Internet Protocol]]"
---

A 32-bit number that indicates the network portion of of an IP Address.

For example, `255.255.255.0` is equivalent to `/24` in [[Classless Inter-domain Routing#CIDR Notation|CIDR Notation]]


| Subnet Mask     | CIDR Notation Subnet Mask | 32-bit Number                       |
| --------------- | ------------------------- | ----------------------------------- |
| 255.255.255.0   | /24                       | 11111111.11111111.11111111.00000000 |
| 255.255.255.240 | /28                       | 11111111.11111111.11111111.11110000 |

# References
https://aws.amazon.com/what-is/cidr/