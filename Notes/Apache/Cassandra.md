---
tags: 
- notes
- database/nosql
- tool
- apache
Draft: false
related-reference-note:: 
- "[[Reference Notes/HelloInterview/System Design/Key Technologies/Cassandra|Cassandra]]"
---

- An open-source distributed NoSQL Database
- Uses Cassandra Query Language(CQL)
	- Very similar to SQL but without the relational functionalities

# Data Model
- Keyspaces
	- equivalent to database in other Database technologies
	- contains multiple tables
- Table - Collection of rows
- Row - record of data
- Column - typed value

# Key Concepts
## Partitioning
- Horizontal partitioning across different nodes
- Use of hashring concept for spreading data across different nodes via [[Notes/Consistent Hashing|Consistent Hashing]]
## Primary Key
- Partition key
- Cluster key
## Replication
- Modes
	- NetworkTopologyStrategy - can replicate across different datacenters. Recommended for production
	- Simple - good for testing
## Consistency
- Each operation can be configured to be strongly or eventually consistent
- Configuration options
	- ONE
	- TWO
	- THREE
	- ALL
	- LOCAL_ONE?
	- QUORUM?
## Query Routing
- query requests are directed to a coordinator node
	- Any node can be a coordinator node
- Coordinator node is responsible for querying other existing nodes
## Storage Engine
LSM - Log structure merge tree
- Commit Log - a [[Write-Ahead Log]]
- Memtable - In-memory data that are to be committed to disk
- SSTABLE - Immutable list of data from Memtable already flushed

## Gossip
- A method in Cassandra nodes of peer-to-peer communication between nodes for discovery
- Each nodes knows every other node
- Has probabilistic bias toward "seed" nodes
	- Seed nodes are nodes that can startup a cluster

## Fault Tolerance
- Has handling for failed nodes
- Administrator has to signify that a node has failed
- Concept of "hinted handoffs" when a request(typically, write request) is sent to a failed node
	- When the failed node sends a heartbeat, hinted handoff is sent to the node

# Advanced Features
## Stored Attached Index
- Global secondary index support for reading
- Allows convenient performant querying of data given an already existing 
## [[Materialized View]]
Cached materialized results of views
## Search Indexing
Can be used along with [[Notes/ElasticSearch|ElasticSearch]]

# References
https://cassandra.apache.org/_/cassandra-basics.html
https://cassandra.apache.org/doc/latest/
https://cassandra.apache.org/doc/latest/cassandra/architecture/storage-engine.html