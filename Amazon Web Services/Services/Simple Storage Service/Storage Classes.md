# S3 Standard
![[Pasted image 20230407042918.png]]
- Objects are stored to at least 3 availability zones

# S3 Standard-IA
Standard Infrequent Access
![[Pasted image 20230407043147.png]]
- Similar to Standard regarding High availability. Differs in pricing model.
# S3 One Zone-IA
![[Pasted image 20230407043509.png]]
- Similar to [[Storage Classes#S3 Standard-IA]] but the main difference is that there is only one AZ.
# S3 Glacier - Instant
![[Pasted image 20230407043828.png]]
- Similar to [[Storage Classes#S3 Standard-IA]], but longer minimum duration charge. Expected for much less frequently accessed data.
# S3 Glacier - Flexible
![[Pasted image 20230408200057.png]]
- <mark style="background: #FFF3A3A6;">Replicated to at least 3 AZs</mark>
- Since bucket is not publicy accessible, requires a <mark style="background: #FFF3A3A6;">flexible retrieval process</mark>
# S3 Glacier - Deep Archive
![[Pasted image 20230408200432.png]]
- Similar to [[Storage Classes#S3 Glacier - Flexible]], but for much longer storage

# S3 Intelligent-Tiering
![[Pasted image 20230408202715.png]]
# References
https://aws.amazon.com/s3/pricing/
https://aws.amazon.com/s3/storage-classes/
https://aws.amazon.com/s3/storage-classes-infographic/