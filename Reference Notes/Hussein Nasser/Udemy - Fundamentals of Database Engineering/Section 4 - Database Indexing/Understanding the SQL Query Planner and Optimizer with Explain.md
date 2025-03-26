---
tags:
  - database
  - reference-notes
Draft: true
---

> [!note] 
> Mostly about `EXPLAIN` 
# Script
```sql
-- EXPLAIN ANALYZE

-- Make sure to run the container with at least 1GB shared memory
-- docker run --name pg --shm-size=1g -e POSTGRES_PASSWORD=postgres --name pg postgres

CREATE TABLE grades (
    id SERIAL PRIMARY KEY,
    g INT,
    name TEXT
);

INSERT INTO grades (g, name)
SELECT
    RANDOM() * 100,
    SUBSTRING(MD5(RANDOM()::TEXT), 0, FLOOR(RANDOM() * 31)::INT)
FROM
    GENERATE_SERIES(0, 500);

VACUUM (ANALYZE, VERBOSE, FULL);

EXPLAIN ANALYZE
SELECT
    id, g
FROM
    grades
WHERE
    g > 80 AND g < 95
ORDER BY
    g;

CREATE INDEX grades_g ON grades (g);
```

# Test Scripts
```sql
EXPLAIN SELECT id, g FROM grades;

EXPLAIN
SELECT * FROM grades
ORDER BY g;

EXPLAIN SELECT id FROM grades;

EXPLAIN SELECT * FROM grades where id = 10;
```

> [!info] 
> Cost - initial value - startup time
> Cost - second value - total time
> Width - average width in bytes per row retrieved
> Rows - Estimated number of row output

# References
https://www.postgresql.org/docs/current/using-explain.html#USING-EXPLAIN-BASICS