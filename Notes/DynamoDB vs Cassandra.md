---
tags:
  - database/nosql
  - comparison
  - tool
Draft: true
Parent:: 
- "[[Notes/AWS/DynamoDB|DynamoDB]]"
- "[[Notes/Apache/Cassandra|Cassandra]]"
---


|                 | DynamoDB                                            | Cassandra                                          |
| --------------- | --------------------------------------------------- | -------------------------------------------------- |
| Secondary Index | Has GSI and LSI                                     | Has [[Notes/Apache/Cassandra\|Cassandra]]          |
| Schema          | Schemaless. Need only to define keys and index keys | Requires schema to define                          |
| Author          | AWS                                                 | Facebook                                           |
| Views           | None                                                | Materialized Views                                 |
| Search Index    | Usable with [[Notes/ElasticSearch\|ElasticSearch]]  | Usable with [[Notes/ElasticSearch\|ElasticSearch]] |
