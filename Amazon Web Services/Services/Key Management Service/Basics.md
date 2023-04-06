----
aliases: [Key Management Service Basics, KMS]
---

![[Pasted image 20230406194011.png]]
> [!important] 
> FIP 140-2 (L2) a security standard used by KMS

> [!note] 
> KMS Keys are previously called Customer Master Key (CMK)


![[Pasted image 20230406210027.png]]
![[Pasted image 20230406211149.png]]

- KMS Keys - max of 4kb each
# Data Encryption Keys (DEKs)
![[Pasted image 20230406211439.png]]
- Generated using KMS Key
- Linked to the KMS key which created it
- Can be used outside of AWS
- KMS doesn't store this DEK in any way. Discards it
- When GenerateDataKey is performed with KMS key, generate:
	- Plaintext version
	- Ciphertext version
- Up to you or the service using KMS to track DEKs
# Key Concepts
![[Pasted image 20230406222515.png]]


# Reference
[AWS KMS concepts](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html)
