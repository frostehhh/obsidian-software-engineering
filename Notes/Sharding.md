---
tags:
  - database
  - notes
Draft: true
"related-reference-note:":
  - "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 7 - Database Sharding/Sharding|Sharding]]"
has-questions: true
similar:: 
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
# Replicas
Master-slave replicas
More masters for better writes
More slaves for better reads

# Copied
Before you Shard, try the following first
1. Understand what your actual problem is before optimizing(too slow reads vs too slow writes)  Analyze your slowest queriers and see why its slow: https://youtu.be/-qNSXK7s7_w?t=237 Create indexes on appropriate columns and tune your data schema.

2. Horizontal Partitioning - Have partition key(mostly on primary key) and split database into different ranges.  This will create smaller B-trees on the indexes.

3. Vertical Partitioning - When you have columns that you rarely access, and you cut a column out of the main database. This will make reads faster for frequent queries and slower for not frequent queries and make your B-trees smaller(less space in memory also)

Partitioning Video: https://www.youtube.com/watch?v=QA25cMWp9Tk
---- << Database still in one machine when you do Partitioning.  Partitioning is done automatically by most modern DB systems and client doesn't have to know any difference).>>--


3. (Read Optimization) Master-Slaves replications, with master handling all writes and slaves handling all reads.  Masters sync with slaves with latest data
4. (Write optimization) Master-Master-Slaves replication in multi-regions(i.e. EAST vs WEST) with multiple masters handling writes, slaves handling reads, sync handled between masters<->masters and masters->read

5. Finally shard when you REALLY have to.  Sharding adds complex client logic and couples with your data base.  You also lose ACID as you cannot guarantee transactions and isolation between your shards.   You can use Vitess to help you manage your sharding query logic https://vitess.io/

# References
https://en.wikipedia.org/wiki/Consistent_hashing