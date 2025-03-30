---
tags:
  - database
  - reference-notes
Draft: true
---

- A mechanism to traverse data row by row
- In PostgreSQL, a pl/pgsql feature

# Example
```sql
DO $$
DECLARE 
	test record;
	students_cursor CURSOR FOR SELECT * FROM students LIMIT 10;
BEGIN
	OPEN students_cursor;
	FETCH students_cursor INTO test;
	RAISE NOTICE '%', test;
END
$$;
```

# Questions
- What's the benefit of using cursors?
- What are good examples of when to use this?
# References
https://en.wikipedia.org/wiki/Cursor_(databases)
https://www.postgresql.org/docs/current/plpgsql-cursors.html
https://www.dbvis.com/thetable/cursors-in-postgresql-a-guide/#:~:text=Cursors%20allow%20you%20to%20fetch,when%20a%20FETCH%20is%20called.
https://www.geeksforgeeks.org/postgresql-cursor/