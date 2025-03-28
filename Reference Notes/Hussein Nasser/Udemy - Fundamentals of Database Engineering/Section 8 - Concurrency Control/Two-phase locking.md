---
tags:
  - database
  - reference-notes
  - computer-science/locks
Draft: true
---

- Select and mark as for update - use [[Exclusive Lock]]
- Perform update as usual. [[Exclusive Lock]] already exists so a new lock is not created
- Ensures a transaction that reads and then writes a record will do so one at a time.
# References
https://en.wikipedia.org/wiki/Two-phase_locking
https://www.postgresql.org/docs/current/sql-select.html#SQL-FOR-UPDATE-SHARE