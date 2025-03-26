---
tags:
  - reference-notes
  - database
  - procedural
Draft: false
---

Practical example via postgres

# Starting up docker

```
--employees table for the indexing lecture

--paste these commands into the postgres

--start the docker instance

docker run --name pg -e POSTGRES_PASSWORD=postgres -d postgres


docker start pg

--run postgres command shell

docker exec -it pg psql -U postgres

--the command should switch to

--postgres=#

-- paste these sql
```

# SQL Script

## Initial
```sql
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name TEXT
);

CREATE OR REPLACE FUNCTION random_string(length INTEGER)
RETURNS TEXT AS $$
DECLARE
    chars TEXT[] := '{0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F,G,H,I,J,K,L,M,N,O,P,Q,R,S,T,U,V,W,X,Y,Z,a,b,c,d,e,f,g,h,i,j,k,l,m,n,o,p,q,r,s,t,u,v,w,x,y,z}';
    result TEXT := '';
    i INTEGER := 0;
    length2 INTEGER := (SELECT TRUNC(RANDOM() * length + 1));
BEGIN
    IF length2 < 0 THEN
        RAISE EXCEPTION 'Given length cannot be less than 0';
    END IF;
    FOR i IN 1..length2 LOOP
        result := result || chars[1 + RANDOM() * (ARRAY_LENGTH(chars, 1) - 1)];
    END LOOP;
    RETURN result;
END;
$$ LANGUAGE plpgsql;

INSERT INTO employees (name)
SELECT random_string(10)
FROM generate_series(0, 1000000);
```

## Index and test scripts
```sql
EXPLAIN ANALYZE SELECT name from employees where id = 1;

EXPLAIN ANALYZE SELECT id from employees where id = 5000;

EXPLAIN ANALYZE SELECT id from employees where name = 'Zs';
EXPLAIN ANALYZE SELECT id, name from employees where name = 'sA';
EXPLAIN ANALYZE SELECT * from employees where name = 'sA';

EXPLAIN ANALYZE SELECT id, name from employees where name like '%ZA%';


CREATE INDEX employees_name on employees(name);
DROP INDEX employees_name;
```

> [!note] 
> Index seems to be based on the filter we include 