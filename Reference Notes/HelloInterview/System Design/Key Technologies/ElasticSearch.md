---
tags:
  - reference-notes
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/elasticsearch
Draft: true
---

- Tool for optimizing searches
- Supports most if not all scenarios necessary for searching

# Concepts
1. Document - record
2. Index - value to search by
3. Mapping - schema of fields
4. Field - a field and its datatype

# Interacting with ElasticSearch via REST API

- Create index
- Create index mapping
- Get query
- Sort Query
- Create document
- Delete(?)
- Update document
	- PUT to replace whole document or
	- POST replace specified data
- Pagination
	- Stateful - internally, reads all pages from x to starting page and drops those pages, and then returns the next page to fulfill size
		- Starting page
		- Size
	- Stateless - finds search_after record and returns page based on size
		- search_after
		- size
		
> [!info]
> This is discussed in [[SQL Pagination with Offset is Very slow]]

# Point in Time search
- Cache pagination results via
```
pit: {
 id: "...",
 keep_alive: "1m"
}
```
- Avoid data inconsistency issues particularly when data is inserted or deleted while navigating pages
# ElasticSearch in System Design
- Complex search scenarios
- Eventual consistency
- Denormalization
- Read-heavy workloads

# ElasticSearch Internals
- ElasticSearch is built on top of [Apache Lucene](https://lucene.apache.org/), a low-level search library
- Internally, consists of multiple nodes, where node is a role. Multiple nodes can be assigned to a server
- ElasticSearch Shard is a wrapper for Lucene Index

## Node Types
- Master
- Ingest
- Data
- Coordinating
- Machine Learning

## Master
- Only 1
- Administrative
- Assigning nodes
- Should be durable, resilient
## Ingest
- Processes new documents
- Send processed documents to Data nodes
## [[Database Indexes#Inverted Indexes|Inverted Indexes]]
- Used for search
## Query Optimization
Queries are optimized via an internal query planner

## Flows

### Accepting new documents
1. Client
2. Ingest Node
3. Data Node
4. return to Ingest node and client
### Querying documents
1. Client node
2. Coordinating node
3. Data nodes
4. Coordinating node receives partial result from each data node queried
5. Merge results in coordinating node
6. Return results to client
