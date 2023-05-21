![[Pasted image 20230408205449.png]]
> [!important] 
> For different account scenario and destination bucket, destination bucket should have a bucket resource policy to define that a role from a separate account can write and replicate buckets in that account. 

# Replication Options
By default, all objects can be replicated.
Can select a subset of objets
![[Pasted image 20230409145540.png]]

# Replication Considerations
![[Pasted image 20230409171220.png]]

> [!note] 
> No Deletes by default but it can be configured. 

# Why use replication
![[Pasted image 20230409172124.png]]
- SRR - Same-region replication
- CRR - Cross-region replication