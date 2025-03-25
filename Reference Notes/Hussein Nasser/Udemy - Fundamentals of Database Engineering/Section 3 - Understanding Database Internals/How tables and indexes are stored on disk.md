---
tags:
  - database
  - reference-notes
  - operating-system
  - data-structures
Draft: false
---

# Logical table
Data is stored in table format - rows + columns

# Row ID
identifier for a row

# Page 
Each page contains a data with a fixed max size. For instance 8kb per page. 

# IO - input output read req
Reads data per page regardless of the query needing only 1 row

# Heap
Data structure used for database data
When querying for data, brute force search

# Index
- Representation of a database table via a certain value or values
- Another "table" data structure is created where each entry is the value + pointer to row in main table
- Sorted so we can optimize the search algorithm

# Clustered index
In most DBMS, primary is usually a clustered index
# References
[[How+tables+and+indexes+are+stored+on+disk.pdf]]