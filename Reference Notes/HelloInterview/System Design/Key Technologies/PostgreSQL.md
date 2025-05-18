---
tags:
  - reference-notes
  - database
  - system-design
Draft: false
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/postgres
---

# Core Capabilities & Limitations
## Read Performance
### Limitations
Table with 100m> rows
Full-text search 10m+ documents
Complex joins with 10m> rows
### Capabilities
- index
	- covering index - include non-key values in index
	- partial index - index a subset of a data given a `WHERE` condition
	- Note: Having indexes slows down writes
- replica
	- master-slave replication
- partition
	- Table partitions
## Write Performance

### Capabilities
- Write-ahead log
- buffer-cache updates
- background writer
- index updates
### Limitations
- 5k/second per core
- Updates with index modification - 1k-2k/second per core
- Complex transactions - hundreds/second
- bulk operations - 10k+ rows per seconds
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
1. Extreme write throughput
2. Global distribution considerations
3. Simple key-value store usage


# Questions
- When to choose pessimistic vs optimistic locking