---
tags:
  - flashcards/security
  - security
---

How the the [[RSA]] algorithm work[^1]
?
1. Client generates pre-master secret(private key)
2. Client encrypts this with the public key from the server.
3. Client send the encrypted pre-master secret to the server
4. The server decrypts the encrypted pre-master secret to get the raw pre-master secret
5. Both sides now have the pre-master secret, client random number, and server random number. The master secret is generated from these values
<!--SR:!2025-05-23,16,290-->
+++

How does the [[Diffie-Hellman Algorithm]] work?[^2]
?
See [[Diffie-Hellman Algorithm]]
<!--SR:!2025-07-16,56,310-->
+++

How does digital signing work?[^3]
?
See [[Notes/Digital Signatures|Digital Signatures]]
<!--SR:!2025-05-22,15,290-->
+++

[^1]: [[RSA]]
[^2]: [[Diffie-Hellman Algorithm]]
[^3]: [[Notes/Digital Signatures|Digital Signatures]]
