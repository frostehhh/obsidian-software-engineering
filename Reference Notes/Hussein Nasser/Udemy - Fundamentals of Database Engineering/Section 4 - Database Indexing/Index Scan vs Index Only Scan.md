---
tags:
  - database
  - reference-notes
  - procedural
Draft: false
similar:: 
- "[[Key vs Non-key column database indexing]]"
---


> [!note] 
> My guess:
> Index-only scan when only an index value is involved in a query as well as the other values included in the index
> Index scan - an index is involved but we need to check the heap. 