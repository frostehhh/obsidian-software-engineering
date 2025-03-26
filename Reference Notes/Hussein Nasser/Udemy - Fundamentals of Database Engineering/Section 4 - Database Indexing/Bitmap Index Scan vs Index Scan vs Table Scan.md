---
tags:
  - database
  - reference-notes
  - procedural
Draft: true
---

Bitmap Index Scan
Bitmap Heap Scan

```sql
-- Bitmap heap scan and bitmap index scan
EXPLAIN SELECT * FROM grades where g > 95;
-- Bitmap heap scan and bitmap index scan
EXPLAIN SELECT id FROM grades where g > 95 ORDER BY id;
-- Index only scan
EXPLAIN SELECT g FROM grades where g > 95;
```

> [!info] 
> Based on my understanding, we use bitmap heap scan when we use an index but we have to access the heap. 
# References
https://stackoverflow.com/questions/6592626/what-is-a-bitmap-heap-scan-in-a-query-plan
http://en.wikipedia.org/wiki/Bitmap_index
https://www.postgresql.org/message-id/12553.1135634231@sss.pgh.pa.us