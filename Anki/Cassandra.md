---
tags:
  - flashcards
---

What is Cassandra and what language does it use for querying?
?
Cassandra is an open-source distributed NoSQL Database that uses Cassandra Query Language (CQL), which is similar to SQL but without relational functionalities.
<!--SR:!2026-05-15,257,330-->
+++

What are the key components of Cassandra's data model?
?
- Keyspaces (equivalent to databases)
- Tables (Collection of rows)
- Rows (record of data)
- Columns (typed value)
<!--SR:!2025-11-16,105,310-->
+++

What internal components does Cassandra's storage engine use?
?
Storage Engine (LSM - Log structure merge tree):
- Commit Log: Write-Ahead Log
- Memtable: In-memory data to be committed to disk
- SSTABLE: Immutable list of data from flushed Memtable
<!--SR:!2026-02-14,124,280-->
+++

How does Cassandra's Gossip Protocol work
?
- Peer-to-peer communication between nodes for discovery
- Each node knows every other node
- Has probabilistic bias toward "seed" nodes for cluster startup
<!--SR:!2025-11-18,36,300-->
+++

How does Cassandra handle fault tolerance
?
- Handles failed nodes
- Uses "hinted handoffs" for write requests to failed nodes
- Failed nodes receive hinted handoffs when they recover (send heartbeat)
<!--SR:!2026-08-05,296,340-->
+++

What are the consistency configuration options available in Cassandra?
?
- ONE
- TWO
- THREE
- ALL
- LOCAL_ONE
- QUORUM
<!--SR:!2026-01-29,165,310-->
+++ 