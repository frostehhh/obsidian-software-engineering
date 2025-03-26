---
tags:
  - database
  - reference-notes
Draft: false
---
# Issue
Writes are blocked while indexes are being created

# Sample
`create index concurrently g on grades(g)`

# References
https://www.postgresql.org/docs/current/sql-createindex.html