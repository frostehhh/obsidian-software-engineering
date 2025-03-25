---
tags:
  - database
  - notes
Draft: false
related-reference-note:: 
- "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 2 - ACID/Consistency|Consistency]]"
Parent:: 
- "[[ACID]]"
---

The property of having consistent data and/or consistent reads

# Data Inconsistency
Literally, inconsistent data.

> [!example] 
>  When we have 2 tables A and B, table A counts total number of person's followers, table records each of the person's followers, but the count in table A does not match the table B records

# Read Inconsistency
While a row is being updated, a separate read transaction reads the initial state of the data. The read obtains outdated data.

> [!example] 
> One case where this can happen is with database read replicas 
