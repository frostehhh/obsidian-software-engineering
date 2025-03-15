![[Pasted image 20230408205449.png]]
> [!important] 
> For different account scenario and destination bucket, destination bucket should have a bucket resource policy to define that a role from a separate account can write and replicate buckets in that account. 

# Replication Options
By default, all objects can be replicated.
Can select a subset of objets
![[Pasted image 20230409145540.png]]
- Batch Replication - option to replicate objects before replication configuration is set
# Replication Considerations
![[Pasted image 20230409171220.png]]

> [!note] 
> No Deletes by default but it can be configured. 

# Why use replication
![[Pasted image 20230409172124.png]]
- SRR - Same-region replication
- CRR - Cross-region replication

# References
[Replicating existing objects with S3 Batch Replication](https://docs.aws.amazon.com/AmazonS3/latest/userguide/s3-batch-replication-batch.html)
