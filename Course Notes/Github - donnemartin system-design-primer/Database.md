### Relational database management system (RDBMS)

A relational database like SQL is a collection of data items organized in tables.

# ACID
Can refer to
[[ACID vs BASE]]

# [Master-slave replication](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#master-slave-replication)

The master serves reads and writes, replicating writes to one or more slaves, which serve only reads. Slaves can also replicate to additional slaves in a tree-like fashion. If the master goes offline, the system can continue to operate in read-only mode until a slave is promoted to a master or a new master is provisioned.

# [Master-master replication](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#master-master-replication)

Both masters serve reads and writes and coordinate with each other on writes. If either master goes down, the system can continue to operate with both reads and writes.


# [Federation](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#federation)

Federation (or functional partitioning) splits up databases by function. For example, instead of a single, monolithic database, you could have three databases: **forums**, **users**, and **products**, resulting in less read and write traffic to each database and therefore less replication lag. Smaller databases result in more data that can fit in memory, which in turn results in more cache hits due to improved cache locality. With no single central master serializing writes you can write in parallel, increasing throughput.



# References

https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#database
