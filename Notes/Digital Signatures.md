---
tags:
  - notes
  - security
Draft: false
related:: 
- "[[Notes/Encryption|Encryption]]"
related-reference-note:: 
- "[[Reference Notes/Adrian Cantrill/Cybersecurity/Digital Signatures/Digital Signatures|Digital Signatures]]"
---

- Digital signature is a way to verify the integrity of the data and the authenticity of who sent it.
- It is a way to prove you got what you need from an expected sender
- Hash = data * hashFn
- Signature = Hash * private key
- Digitally signed data = original data + signature

# Components
1. Data
2. Hash function
3. Private key for "signing" the hash
4. Public key for decryption of "signed" hash
# Flow

![[Pasted image 20230107213156.png]]
1. Bob signs with his private key the hash created from the original data. The signature created and the data forms the Digitally Signed Data
2. He sends the digitally signed data to another person.
3. The receiver creates a new hash from the received data.
4. The receiver uses his public key to get the original hash from the signature of the data.
5. The receiver confirms that the hash created in step 3 and step 4 are identical. Thus, the data is verified.