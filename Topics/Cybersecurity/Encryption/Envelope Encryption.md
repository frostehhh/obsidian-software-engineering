# Encryption
![[Pasted image 20230517042859.png]]
- Main key, which is KEK, never leaves KMS. User does not need to know the value. 
- When a bad actor happens to decrypt the encrypted DEK, it can only be used to decrypt that one ciphertext. This limits the data that is leaked.
# Decryption
![[Pasted image 20230517043205.png]]

# Considerations
![[Pasted image 20230517043342.png]]