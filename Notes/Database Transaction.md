---
tags:
  - database
  - notes
Draft: false
aliases: 
- Transaction
related-reference-note:: 
- "[[Database Transaction]]"
- "[[Write-Ahead Log]]"
- "[[How tables and indexes are stored on disk]]"
---

- A transaction is a collection of queries that must all succeed or fail together
- Relevant keywords
	- BEGIN
	- COMMIT
	- ROLLBACK
	- END?
- Used for grouping related data modifications
- Can also be used for just reading
- Purpose is to maintain a snapshot of the database's state for the entirety of a transaction
- Uses [[Write-Ahead Log|WAL]] for durability and recovery
- Operates on [[How tables and indexes are stored on disk|database pages]]
- 