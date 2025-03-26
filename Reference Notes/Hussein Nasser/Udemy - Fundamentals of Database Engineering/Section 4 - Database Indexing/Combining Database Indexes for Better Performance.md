---
tags:
  - database
  - reference-notes
  - procedural
Draft: false
---

# When multiple indices are used in `WHERE`
BitmapAnd
BitmapOr


```sql
CREATE INDEX ON test (a)
CREATE INDEX ON test (b)

-- Uses both indices (a) and (b)
EXPLAIN ANALYZE SELECT c FROM test WHERE a = 70 AND b = 80
-- Uses both indices (a) and (b)
EXPLAIN ANALYZE SELECT c FROM test WHERE a = 70 OR b = 80


---- Composite index (a,b)
CREATE INDEX on test (a,b)

-- uses composite index (a,b)
EXPLAIN ANALYZE SELECT c FROM test WHERE a = 70 AND b = 80

-- DOES NOT use composite index (a,b)
EXPLAIN ANALYZE SELECT c FROM test WHERE a = 70 OR b = 80

---- Composite index(a,b) and index(b)
CREATE INDEX on test (a,b)
CREATE INDEX ON test (b)
-- uses composite index (a,b)
EXPLAIN ANALYZE SELECT c FROM test WHERE a = 70 AND b = 80

-- Uses composite index (a,b) and index (b)
EXPLAIN ANALYZE SELECT c FROM test WHERE a = 70 OR b = 80
```
