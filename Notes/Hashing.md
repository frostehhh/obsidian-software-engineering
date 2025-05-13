---
tags:
  - security
  - notes
  - cryptography
"related-reference-note:":
  - "[[Reference Notes/Adrian Cantrill/Cybersecurity/Hashing/Hashing|Hashing]]"
---
- One-way conversion of plaintext to another presentation
- Impossible to get the original plaintext from a hash
- Used for data verification

# Algorithms
- MD5
- SHA2-256

![[Pasted image 20230107183054.png]]

# Example
![[Pasted image 20230107183859.png]]

Hashed password can be used for security purposes. Hackers cannot exploit this information when they find the hashed password in the server's database because it is not easy to revert them to the original format.

# Hashing Weakness - Collision
![[Pasted image 20230107184028.png]]
With a faulty hashing algorithm, it is possible to create the same hash from 2 different data resulting in a collision

# References
[https://marc-stevens.nl/research/papers/MTh%20Marc%20Stevens%20-%20On%20Collisions%20for%20MD5.pdf](https://marc-stevens.nl/research/papers/MTh%20Marc%20Stevens%20-%20On%20Collisions%20for%20MD5.pdf)[https://natmchugh.blogspot.com/2015/02/create-your-own-md5-collisions.html](https://natmchugh.blogspot.com/2015/02/create-your-own-md5-collisions.html)
[https://www.sentinelone.com/cybersecurity-101/hashing/](https://www.sentinelone.com/cybersecurity-101/hashing)