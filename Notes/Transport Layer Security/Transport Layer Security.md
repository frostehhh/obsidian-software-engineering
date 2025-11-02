---
tags:
  - notes
  - backend
  - networking/communication
  - networking
  - security
Draft: false
aliases:
  - TLS
"related-reference-note:":
  - "[[TLS]]"
  - "[[SSL and TLS]]"
---

# Transport Layer Security
TLS is a protocol for a client and a server to agree to use a symmetric key to encrypt data sent between each other. Prior to data communication, a handshake is performed with asymmetric keys to acquire the symmetric key to be used.

# Flow
## Connection Establishment
### How do we communicate?
1. Client sends a hello request containing a <font color="#76923c">client random number</font> and communication protocols supported
2. Server responds with a response containing info such as communication protocols, server certificate and <font color="#5f497a">server random number</font> ^3e2368
### Client authenticates server identity
1. In [[#^3e2368]], we can include information for the server to send a server certificate containing a public key.
2. Client validates the certificate via a public trusted [[Certificate Authority]]
## Key Exchange
Can use key exchange algorithms like [[RSA]] or [[Diffie-Hellman Algorithm]]

![[TLS 1.2]]


![[Diffie-Hellman Algorithm#Diffie-Hellman Algorithm]]

![[TLS 1.3]]
![[TF-GEN-SSLTLS.png]]
# References
https://www.thesslstore.com/blog/tls-1-3-handshake-tls-1-2/
![[TLS#References]]