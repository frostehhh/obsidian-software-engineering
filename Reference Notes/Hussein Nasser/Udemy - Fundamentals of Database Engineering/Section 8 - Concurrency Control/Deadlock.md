---
tags:
  - database
  - reference-notes
  - computer-science
Draft: true
---

Processes are waiting for each other to finish, but none proceed. Thus, infinitely waiting

# Example
- Create 2 different transactions

## T1
```sql
BEGIN TRANSACTION;
INSERT INTO test values(21);
INSERT INTO test values(20);
```
## T2
```sql
BEGIN TRANSACTION;
INSERT INTO test values(20);
INSERT INTO test values(21);
-- After this, deadlock error will be detected by postgres
```
# References
https://en.wikipedia.org/wiki/Deadlock_(computer_science)