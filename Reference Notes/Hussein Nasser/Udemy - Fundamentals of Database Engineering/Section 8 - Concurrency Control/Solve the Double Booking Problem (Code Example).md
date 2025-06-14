---
tags:
  - database
  - reference-notes
  - computer-science/locks
Draft: false
---

 This is an example for [[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 8 - Concurrency Control/Two-phase locking]]

Alternative solution is to rely on implicit exclusive lock created by the DB internally where [[Notes/ACID/Isolation#Isolation Levels|isolation level]] is read committed

# T1
```sql
BEGIN;

UPDATE users
   SET name = 'new 1'
 WHERE id = 1
   AND name = 'test';
   
COMMIT;

```

# T2
```sql
BEGIN;

UPDATE users
   SET name = 'new 2'
 WHERE id = 1
   AND name = 'test';
--- this will result to UPDATE 0 because name = 'test' no longer exists. Seems similar to having a version column
   
COMMIT;
```