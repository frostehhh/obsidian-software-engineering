---
tags:
  - database
  - notes
Draft: false
related-reference-note:: 
- "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 2 - ACID/Durability|Durability]]"
Parent:: 
- "[[ACID]]"
---

Resistance to data corruption in the event of crashes.
# Methods to implement
- Write-ahead log(WAL) - compressed version of changes
- Asynchronous replication - expensive
- AOF - append-only file

# OS Cache
- When writes are being done by an OS, the data is moved to OS cached by default
- Fsync can be used to force writes to disk and bypass the OS cache. Expensive
