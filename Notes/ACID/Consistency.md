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

# Read Inconsistency
While a row is being updated, a separate read transaction reads the initial state of the data. The read obtains outdated data.

- One case where this can happen is with database read replicas
