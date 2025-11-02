---
tags:
  - notes
  - backend
  - networking/communication/protocols
  - networking
  - security
Draft: false
"Parent:":
  - "[[Notes/Transport Layer Security/Transport Layer Security|TLS]]"
"related-reference-note:":
  - "[[SSL and TLS]]"
---

# TLS 1.3
- 1 round trip handshake

# Flow
## Key Exchange
The flow goes as follows(uses Diffie-Hellman Algorithm):
1. The client generates their own private key
2. The client uses the public key to encrypt the private key
3. The server receives the encrypted client's private key
4. The server generates their own private key
5. The server encrypts the client's encrypted private key.
6. The server returns as a response the server private key encrypted via the public key
7. The client received the response from the server and encrypts the received key with the client private key.
8. Both the client and the server obtain a copy of a symmetric key.

![[Pasted image 20250323171642.png]]
## With 0RTT
![[Pasted image 20250323173529.png]]