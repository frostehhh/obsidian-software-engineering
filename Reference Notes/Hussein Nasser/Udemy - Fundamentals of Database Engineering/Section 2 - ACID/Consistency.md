---
tags:
  - database
  - reference-notes
Draft: false
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


> [!warning]
> Information provided seems incorrect. The consistency here seems to be referring to consistency in CAP Theorem. However, I'm not sure where data inconsistency came from
