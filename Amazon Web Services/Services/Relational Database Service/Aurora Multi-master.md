![[Pasted image 20230502051110.png]]
![[Pasted image 20230502051342.png]]

# Failover
## Single-Master
![[Pasted image 20230502051615.png]]

## Multi-Master

Federation (or functional partitioning) splits up databases by function. For example, instead of a single, monolithic database, you could have three databases: **forums**, **users**, and **products**, resulting in less read and write traffic to each database and therefore less replication lag. Smaller databases result in more data that can fit in memory, which in turn results in more cache hits due to improved cache locality. With no single central master serializing writes you can write in parallel, increasing throughput.