---
tags:
  - database
  - notes
Draft: false
related-reference-note:: 
 - "[[Shared vs Exclusive Locks]]"
opposite:: 
 - "[[Exclusive Lock]]"
---
- I want to read this row and will acquire a shared lock if there isn't one yet. Other people can also use the shared lock to read, but no one can write.
- Cannot exist with [[Exclusive Lock]]
- read lock