![[Pasted image 20230107204232.png]]


![[Pasted image 20230107213156.png]]

1. Bob signs with his private key the hash created from the original data. The signature created and the data forms the Digitally Signed Data
2. He sends the digitally signed data to another person.
3. The receiver creates a new hash from the received data.
4. The receiver uses his public key to get the original hash from the signature of the data.
5. The receiver confirms that the hash created in step 3 and step 4 are identical. Thus, the data is verified.