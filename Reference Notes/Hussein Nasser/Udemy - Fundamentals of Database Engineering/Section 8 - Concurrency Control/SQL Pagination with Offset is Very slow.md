---
tags:
  - database
  - reference-notes
Draft: FALSE
---

Using `OFFSET` internally reads x amount of rows to offset, drops them, and then retrieves the next rows.
- Due to reading of rows that will not be returned, performance is wasted
- Solution - rely on row data to simulate offset. For example, we can have a custom `rowId` column. When querying a certain "page", filter like `rowId > 1000 LIMIT 10`
# References
https://www.postgresql.org/docs/current/queries-limit.html