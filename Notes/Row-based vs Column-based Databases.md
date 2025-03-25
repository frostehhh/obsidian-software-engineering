---
tags:
  - database
  - notes
  - comparison
Draft: true
"related-reference-note:":
  - "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 3 - Understanding Database Internals/Row-based vs Column-based Databases|Row-based vs Column-based Databases]]"
has-questions: true
---

# Outline
- row-oriented database(row store)
- column-oriented database(column store)

# Row-oriented Database
- Data is stored per row
- Each row contains all column data
- Optimal for most reads and writes
- Good for complex queries and filters

# Column-oriented Database
- Data is stored per column
- Each block of data contains values from the same column
- Each column value is paired with the rowID pointer
- Blocks are sorted by column
- Good for aggregation
- Bad for complex queries and reading many rows of data
- OLAP

# Pros and Cons
![[Row-based database and column-based database pros and cons.png]]

# Questions
- What if a row spans 2 or more pages?
	- is this possible?
		Answer: https://learn.microsoft.com/en-us/sql/relational-databases/pages-and-extents-architecture-guide?view=sql-server-ver16.
		No. There is a concept of row 
- What happens if we insert a row?
	- between pages?