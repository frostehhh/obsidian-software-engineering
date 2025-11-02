---
tags:
  - reference-notes
  - security
  - backend
  - networking/communication
  - networking
aliases:
  - Secure Sockets Layer and Transport Layer Security
---

**[[Secure Sockets Layer|SSL]] and [[Reference Notes/Adrian Cantrill/Cybersecurity/SSL and TLS/Transport Layer Security|TLS]] both provide**
- Privacy and Data Integrity between client and server
- Privacy - communications are encrypted. See also [[Notes/Encryption]]
- Identity (server or client/server) verified
- Reliable connection - protect against alteration

> [!note] 
> [[TLS]] is just a more secure and updated version of [[Secure Sockets Layer|SSL]] 

### Examples

![[TF-GEN-SSLTLS.png]]
1. Determining communication protocol and cipher suites
2. Authenticate server certificate and verifies the server has a private key for the next step
3. Asymmetric to symmetric encryption
#### Cipher Suite
- set of protocols used by [[TLS]]. Includes these algorithms
	- Algorithms included in a Cipher Suite
		- Key exchange algorithm
		- Bulk encryption algorithm
		- Message authentication code algorithm (MAC)
	- Specific versions of these tied together are known as a cipher suite 
	- In the first step, the client does a client HELLO
		- See diagram for components of this HELLO
	- Afterwards a server HELLO is returned (See diagram for components)
> [!important] 
> TLS also validates the identity of the server 

#### Authentication
The client needs to be able to validate that the server certificate that that the server provdes is valid, that its Public key is valid and that the server itself is valid.

> [!note] 
> A server certificate contains the server public key, DNS name and other organizational information.
> 
> There's another entity involved here known as Public Certificate Authority or CA, which are trusted by your browser and operating system
> 
> In the past for example, catagram.io server created a public/private key pair and a Certificate Signing Request(CSR) sent to a CA after which a signed certificate is generated.
> 
> This means that your browser or OS trusts that certificate as long as it recognizes the CA signature.

In this step, we authenticate the server certificate first by checking the data it contains.

Next, the client sends random data that is encrypted with a public key. It checks if the server can send the same data with the private key that it has. 

#### Key Exchange

From previous steps, we use asymmetric encryption. Here we will use symmetric encryption. The client generates a <mark style="background: #FFF3A3A6;">pre-master key</mark> encrypted with the public key. Then, the server decrypts the pre-master key using its private key.

Both sides use the pre-master key to generate the <mark style="background: #FFF3A3A6;">master secret</mark> which is used to generate the ongoing <mark style="background: #FFF3A3A6;">session keys</mark> which encrypt and decrypt data.


### References
https://learn.cantrill.io/courses/2022818/lectures/45660745