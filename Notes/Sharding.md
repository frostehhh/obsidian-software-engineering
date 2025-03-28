---
tags:
  - database
  - notes
Draft: false
"related-reference-note:":
  - "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 7 - Database Sharding/Sharding|Sharding]]"
has-questions: true
"similar:":
  - "[[Notes/Partitioning|Partitioning]]"
---

# What is sharding
Splitting of a database table into multiple database servers
![[Pasted image 20250327215051.png]]
# Consistent Hashing
A hashing function that gives always gives the same output for an input.

# Pros
- Scalability
	- Data - Smaller table and index size
	- Memory
- Security(users can access certain shards)

# Cons
- Client has to be aware of shards
- Cross-shard transactions
	- Transactions
	- Rollbacks
	- Joins
- Schema changes

# When should you consider Sharding?
- Sharding is a last resort due to its cons related to needing data from different shards in a query

## Before that
### Troubleshoot the system
- Is there some way on the code side to optimize? Can we implement caching in the service level? Load balancer?
- Can the query be optimized? Are there redundant conditions in the query? Can it be simplified?

# Database
- Do we need a table index?
- Can we redesign the database table?
- Can we lessen the columns in the tables?
- Can we redesign the database table as well as related tables?
## Partition
- Horizontal partitioning
- Vertical partitioning
## Replicas
Master-slave replicas
More masters for better writes
More slaves for better reads
# References
https://en.wikipedia.org/wiki/Consistent_hashing