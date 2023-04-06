- Objects are encrypted in S3 buckets, and not the buckets themselves

![[Pasted image 20230406234424.png]]
- context for encryption is when data is at rest
 ![[Pasted image 20230407000431.png]]
![[Pasted image 20230407001150.png]]
- Customer manages the keys themselves, but the cryptographic actions are done by AWS S3

![[Pasted image 20230407024618.png]]

- Root key for S3 instance. 
- AES25 Encryption algorithm
 
![[Pasted image 20230407024658.png]]
- Handled by KMS. It is an AWS managed KMS key
- Aside from root key, each object has its own key generated via the KMS key. This is also a [[Amazon Web Services/Services/Key Management Service/Basics#Data Encryption Keys (DEKs)|DEK]]. Root key encrypts unique key

![[Pasted image 20230407025127.png]]
![[Pasted image 20230407025855.png]]

# References
[https://docs.aws.amazon.com/AmazonS3/latest/user-guide/default-bucket-encryption.html](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/default-bucket-encryption.html)
[https://docs.aws.amazon.com/kms/latest/developerguide/services-s3.html](https://docs.aws.amazon.com/kms/latest/developerguide/services-s3.html)
[https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingKMSEncryption.html](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingKMSEncryption.html)
[https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingServerSideEncryption.html](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingServerSideEncryption.html)
[https://docs.aws.amazon.com/AmazonS3/latest/dev/ServerSideEncryptionCustomerKeys.html](https://docs.aws.amazon.com/AmazonS3/latest/dev/ServerSideEncryptionCustomerKeys.html)