---
tags:
  - database
  - reference-notes
  - 
Draft: false
---

- A method of caching
- hashFn(val) % bitsize = position in bloom filter buffer
- memory efficient
- Tendency to have collisions due to using hash function. Smaller buffer = more collisions, bigger buffer = less collisions

# When to use?
As opposed to caching solutions like Redis, use for efficient lookups but preference for using low amount of memory

# References
[[bloom-filter.pdf]]
https://blog.algomaster.io/p/bloom-filters