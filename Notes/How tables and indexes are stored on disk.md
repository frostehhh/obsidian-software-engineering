---
tags:
  - database
  - notes
  - operating-system
  - data-structures
Draft: false
related-reference-note:: 
- "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 3 - Understanding Database Internals/How tables and indexes are stored on disk|How tables and indexes are stored on disk]]"
- "[[Database Indexes]]"
- "[[Database Transaction]]"
---

- Databases store data in fixed block/page sizes(8kb per block in PostgreSQL, 16kb per block, etc.)
- Querying data -> querying pages of data
- Data is stored in heap data structure
- Index = [[B-Tree and B+ Tree|B-tree]] representations of a table - sorted
- For more details on different types of indexes, see [[Database Indexes]]
- Transactions ([[Database Transaction]]) operate on these pages of data
