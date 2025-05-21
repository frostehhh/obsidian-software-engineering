---
tags:
  - reference-notes
  - backend
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/cassandra
Draft: false
has-questions: true
---

An open-source distributed NoSQL Database
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
##  Storage Model
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

# How to use Cassandra
## Discord Message Channels
### Initial schema
Contains channel_id and message_id as primary keys
### Issue
Some channels have very high load of messages resulting to hot partitions and degraded performance for those partitions
### Developed schema
Add `bucket: int`, which represents 10 days of data, to primary key
### Result
Channel messages are spread across different partitions to avoid hot partition. Performance fixed

## TicketMaster
### Issue
Some events have very high traffic. Hot partitions
### Initial Schema
Primary key -> `event_id`, `seat_id`

### Developed Schema
Add `section_id` to primary key
### Result
All event data are spread across different partitions
# Advanced Features
## Stored Attached Index
- Global secondary index support for reading
- Allows convenient performant querying of data given an already existing 
## Materialized Views
Cached materialized results of views
## Search Indexing
Can be used along with [[Notes/ElasticSearch|ElasticSearch]]
# Cassandra in System Design
- fast read and write
- Highly scalable
- No need for relational data, complex joins or queries
- availability over consistency
# Questions
- is it schemaless. no
- how do you define a cassandra schema
- 