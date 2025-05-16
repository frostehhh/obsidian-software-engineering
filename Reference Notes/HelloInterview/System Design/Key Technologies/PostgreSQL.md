---
tags:
  - reference-notes
  - database
  - system-design
Draft: true
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/postgres
---

# Core Capabilities & Limitations
## Read Performance
- <font color="#d83931">index</font>
	- covering index - include non-key values in index
	- partial index - index a subset of a data given a `WHERE` condition
	- Note: Having indexes slows down writes
- replica
	- master-slave replication
- partition
	- Table partitions
## <font color="#d83931">Write Performance</font>


## Replication
Synchronous - strongly consistent
Asynchronous - eventually consistent


## Data Consistency
- Configurable isolation levels
	- read committed(default)
	- repeatable read
	- Serializable
- Supports row-locking
# When to Use PostgreSQL
- Use PostgreSQL as a default. Why?
	- Scales well especially with proper design
	- Robust querying capabilities
	- replicas to improve writes
	- partitions
	- Supports complex joins and queries
# When to consider other options


# Questions
- When to choose pessimistic vs optimistic locking