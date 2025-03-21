---
tags:
  - notes
  - backend/communication
  - backend/networking
Draft: true
aliases:
  - TLS
related-reference-note:: [[TLS]]
---

# Transport Layer Security
TLS is a protocol for a client and a server to agree to use a symmetric key to encrypt data sent between each other. Prior to data communication, a handshake is performed with asymmetric keys to acquire the symmetric key to be used.


# TLS 1.2
Uses RSA


![[Diffie-Hellman Algorithm]]

# TLS 1.3
The flow goes as follows
1. The client generates their own private key
2. The client uses the public key to encrypt the private key
3. The server receives the encrypted client's private key
4. The server generates their own private key
5. The server encrypts the client's encrypted private key.
6. The server returns as a response the server private key encrypted via the public key
7. The client received the response from the server and encrypts the received key with the client private key.
8. Both the client and the server obtain a copy of a symmetric key.

![[TLS#References]]