---
tags:
  - notes
  - backend
  - networking/communication
  - networking
  - security
  - cryptography/protocols
Draft: false
"Parent:": "[[Notes/Transport Layer Security/Transport Layer Security|TLS]]"
"related-reference-note:":
  - "[[SSL and TLS]]"
---

- Uses [[RSA]], [[Diffie-Hellman Algorithm]]
- Flawed due to forward secrecy vulnerability
- 2 round trip handshake
## Key Exchange(RSA)
1. Client generates pre-master secret(private key)
2. Client encrypts this with the public key from the server.
3. Client send the encrypted pre-master secret to the server
4. The server decrypts the encrypted pre-master secret to get the raw pre-master secret
5. Both sides now have the pre-master secret, <font color="#76923c">client random number</font>, and <font color="#5f497a">server random number</font>. The master secret is generated from these values

![[Pasted image 20250323171836.png]]