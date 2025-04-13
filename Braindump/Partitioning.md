---
Draft: false
---

A way to divide a database table into multiple tables in the same system

- Pros
	- Efficient single partition query
	- More options for querying - seq scan vs scattered index scan
- Cons
	- Whole table scans may be more efficient than querying separated partitions
	- Schema changes may be problematic
	- Slow when need to move rows from partition to another partition