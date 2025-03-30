---
tags:
  - database
  - notes
Draft: false
"related-reference-note:":
  - "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 9 - Database Replication/Database Replication|Database Replication]]"
  - "[[Reference Notes/Github - donnemartin system-design-primer/Database|Database]]"
---

# Master-Backup
- 1 master to handle writes
- Backups handle reads
- Synchronization of master to backups cause eventual consistency
# Multi-Master Replication
- Multiple masters accept writes
- Data conflicts may occur. Ex. A write for the same record is handled by Master A and Master B
- Other points are similar to [[#Master-Backup]]

# [[Synchronous]] vs [[Asynchronous]] Replication
## [[Synchronous]]
- A write transaction is considered complete when written in master and backups
- Write is block while syncing to backups
- Sample config options - first 2, first 1, any
## [[Asynchronous]]
- Writes to masters are non-blocking
- Changes are written async to backups

## Pros and Cons
### Pros
- horizontal scalability
- Can have region-based queries
### Cons
- Eventual consistency
- Can be complex to implement
- Slow-writes with synchronous replication