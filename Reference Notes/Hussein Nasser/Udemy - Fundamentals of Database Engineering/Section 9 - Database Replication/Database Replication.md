---
tags:
  - database
  - reference-notes
Draft: true
---

# Master-Backup
- 1 master to handle writes
- Backups handle reads
- Synchronization of master to backups cause eventual consistency
# Multi-Master Replication
- Multiple masters accept writes
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
# References
[[Replication.pdf]]
