---
tags:
  - reference-notes
  - backend
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/kafka
Draft: true
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

# Questions
- log structured merge tree