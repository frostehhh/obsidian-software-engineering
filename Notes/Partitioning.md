---
tags:
  - database
  - notes
  - procedural
Draft: true
"related-reference-note:":
  - "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 6 - Database Partitioning/Partitioning]]"
---

# What is Partitioning?
Splitting of a database table into multiple tables with the same schema

# Horizontal vs Vertical Partitioning
- Horizontal partitioning splits rows into partitions
	- Example - 100 rows split into 5 partitions with 20 rows each
- Vertical partitioning splits columns into partitions

# Types
## By Range
- Dates, ids
## By List
Discrete values
Example: States, Countries, zip codes
## By Hash
Hash functions
Cassandra DB

# Horizontal Partitioning vs Sharding
- Partitioning is done in the same system
	- Table name changes
- Sharding splits a database table into multiple database servers
	- table name persists

# Pros
- Improves query performance when accessing a single partition
- Sequential scan vs scattered index scan
	- Scattered index scan travel from index to heap alternatively and continuously
	- Sometimes seq scan is better
- Easy bulk loading (attach partition)
	- Can create table and attach to partition table
- Archive old data are barely accessed into cheap storage

# Cons

# References
https://www.postgresql.org/docs/current/ddl-partitioning.html