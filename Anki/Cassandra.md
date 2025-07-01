---
tags: flashcards
---

What is Cassandra and what language does it use for querying?
?
Cassandra is an open-source distributed NoSQL Database that uses Cassandra Query Language (CQL), which is similar to SQL but without relational functionalities.
<!--SR:!2025-08-30,60,310-->
+++

What are the key components of Cassandra's data model?
?
- Keyspaces (equivalent to databases)
- Tables (Collection of rows)
- Rows (record of data)
- Columns (typed value)
<!--SR:!2025-07-02,7,270-->
+++

What internal components does Cassandra's storage engine use?
?
Storage Engine (LSM - Log structure merge tree):
- Commit Log: Write-Ahead Log
- Memtable: In-memory data to be committed to disk
- SSTABLE: Immutable list of data from flushed Memtable
+++

How does Cassandra's Gossip Protocol work
?
- Peer-to-peer communication between nodes for discovery
- Each node knows every other node
- Has probabilistic bias toward "seed" nodes for cluster startup
+++

How does Cassandra handle fault tolerance
?
- Handles failed nodes
- Uses "hinted handoffs" for write requests to failed nodes
- Failed nodes receive hinted handoffs when they recover (send heartbeat)
+++

What are the consistency configuration options available in Cassandra?
?
- ONE
- TWO
- THREE
- ALL
- LOCAL_ONE
- QUORUM
<!--SR:!2025-07-06,11,270-->
+++ 