---
tags:
  - pattern
  - database
aliases:
  - WAL
Draft: false
related-reference-note::
  - "[[Database Transaction]]"
  - "[[How tables and indexes are stored on disk]]"
---

- A log used to document in advance the operations to be done
- Used as a means of [[Notes/ACID/Durability|Durability]]
- Critical component for [[Database Transaction]] recovery and durability
- Records changes before they are written to the actual [[How tables and indexes are stored on disk|data pages]]