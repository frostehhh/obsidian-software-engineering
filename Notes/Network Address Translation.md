---
tags:
  - notes
  - networking
  - backend
  - communication
Draft: false
aliases: NAT
related-reference-note:: 
 - "[[Reference Notes/Adrian Cantrill/Networking/OSI 7-Layer Model/Network/Network Address Translation/Network Address Translation|Network Address Translation]]"
---

# Network Address Translation
A protocol for converting private IP address + port to external IP + port through a gateway.

# Types
## One to One NAT
A sender's private IP + Port is converted to public IP + Port.
The receiver can communicate back with no restrictions

# Address Restricted NAT
A client can receive requests only from IP Addresses it knows or has communicated with before

## Example

**Gateway NAT Table**

| Private IP | Private Port | Public IP | Public Port | Destination IP | Destination Port |
| ---------- | ------------ | --------- | ----------- | -------------- | ---------------- |
| 10.0.0.2   | 8992         | 5.5.5.5   | 3333        | 4.4.4.4        | 80               |
| 10.0.0.2   | 9999         | 5.5.5.5   | 4444        | 3.3.3.3        | 80               |

**Incoming external packets**

| Source IP                     | Source Port | Destination IP    | Destination Port | Is Accepted |
| ----------------------------- | ----------- | ----------------- | ---------------- | ----------- |
| 3.3.3.3                       | 80          | 5.5.5.5           | 3333             | Yes         |
| <font color="#ff0000">7.7.7.7 | 80          | 5.5.5.5   </font> | 3333             | No          |

# Port Restricted NAT
A client can receive requests only from IP Address + Port combinations it knows or has communicated with before

## Example

**Gateway NAT Table**

| Private IP | Private Port | Public IP | Public Port | Destination IP | Destination Port |
| ---------- | ------------ | --------- | ----------- | -------------- | ---------------- |
| 10.0.0.2   | 8992         | 5.5.5.5   | 3333        | 4.4.4.4        | 80               |
| 10.0.0.2   | 9999         | 5.5.5.5   | 4444        | 3.3.3.3        | 80               |

**Incoming external packets**

| Source IP                            | Source Port                      | Destination IP | Destination Port | Is Accepted |
| ------------------------------------ | -------------------------------- | -------------- | ---------------- | ----------- |
| 3.3.3.3                              | 80                               | 5.5.5.5        | 3333             | Yes         |
| 4.4.4.4                              | <font color="#ff0000">443</font> | 5.5.5.5        | 4444             | No          |
| <font color="#ff0000">7.7.7.7</font> | 80                               | 5.5.5.5        | 4444             | No          |
| 3.3.3.3                              | 80                               | 5.5.5.5        | 2222             | Yes         |

# Symmetric NAT
A client can receive requests only from IP Address + Port combinations it knows or has communicated with before. The full private IP Address + Port and external IP Address + port combination must be exactly matching

## Example

**Gateway NAT Table**

| Private IP | Private Port | Public IP | Public Port | Destination IP | Destination Port |
| ---------- | ------------ | --------- | ----------- | -------------- | ---------------- |
| 10.0.0.2   | 8992         | 5.5.5.5   | 3333        | 4.4.4.4        | 80               |
| 10.0.0.2   | 9999         | 5.5.5.5   | 4444        | 3.3.3.3        | 80               |

**Incoming external packets**

| Source IP                            | Source Port                      | Destination IP | Destination Port                  | Is Accepted |
| ------------------------------------ | -------------------------------- | -------------- | --------------------------------- | ----------- |
| 3.3.3.3                              | 80                               | 5.5.5.5        | 3333                              | Yes         |
| 4.4.4.4                              | <font color="#ff0000">443</font> | 5.5.5.5        | 4444                              | No          |
| <font color="#ff0000">7.7.7.7</font> | 80                               | 5.5.5.5        | 4444                              | No          |
| 3.3.3.3                              | 80                               | 5.5.5.5        | <font color="#ff0000">2222</font> | No          |
