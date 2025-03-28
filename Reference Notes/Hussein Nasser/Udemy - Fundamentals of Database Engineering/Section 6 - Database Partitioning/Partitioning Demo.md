---
tags:
  - database
  - reference-notes
  - procedural
Draft: false
---

grades_org
index on g

grades_parts
g0035
g3560
g60100

```sql
Insert into grades_parts select * grades_org where...
```

Can create index on grades_parts -> This will be used by the partition tables

ENABLE_PARTITION_PRUNING - optimizes queries for partitions

# References
https://www.postgresql.org/docs/current/ddl-partitioning.html