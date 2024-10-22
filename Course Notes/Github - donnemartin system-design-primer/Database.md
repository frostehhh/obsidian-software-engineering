# Relational database management system (RDBMS)

A relational database like SQL is a collection of data items organized in tables.

## ACID
Can refer to
[[ACID vs BASE]]

## [Master-slave replication](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#master-slave-replication)

The master serves reads and writes, replicating writes to one or more slaves, which serve only reads. Slaves can also replicate to additional slaves in a tree-like fashion. If the master goes offline, the system can continue to operate in read-only mode until a slave is promoted to a master or a new master is provisioned.

## [Master-master replication](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#master-master-replication)

Both masters serve reads and writes and coordinate with each other on writes. If either master goes down, the system can continue to operate with both reads and writes.


## [Federation](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#federation)

Federation (or functional partitioning) splits up databases by function. For example, instead of a single, monolithic database, you could have three databases: **forums**, **users**, and **products**, resulting in less read and write traffic to each database and therefore less replication lag. Smaller databases result in more data that can fit in memory, which in turn results in more cache hits due to improved cache locality. With no single central master serializing writes you can write in parallel, increasing throughput.

## [Sharding](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#sharding)

Distributes a subset of data to different databases

## [Denormalization](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#denormalization)

Denormalization attempts to improve read performance at the expense of some write performance. Redundant copies of the data are written in multiple tables to avoid expensive joins.

## [SQL Tuning](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#sql-tuning)

SQL tuning is a broad topic and many [books](https://www.amazon.com/s/ref=nb_sb_noss_2?url=search-alias%3Daps&field-keywords=sql+tuning) have been written as reference.

It's important to **benchmark** and **profile** to simulate and uncover bottlenecks.

- **Benchmark** - Simulate high-load situations with tools such as [ab](http://httpd.apache.org/docs/2.2/programs/ab.html).
- **Profile** - Enable tools such as the [slow query log](http://dev.mysql.com/doc/refman/5.7/en/slow-query-log.html) to help track performance issues.

Benchmarking and profiling might point you to the following optimizations.
- Tighten up the schema
- use good indices
- Avoid expensive joins
- Partition tables
- Tune the query cache

# [NoSQL](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#nosql)
NoSQL is a collection of data items represented in a **key-value store**, **document store**, **wide column store**, or a **graph database**

## See also
[[Database Refresher & Models#NoSQL Databases]]

# [SQL vs NoSQL](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#sql-or-nosql)


# References

https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#database
