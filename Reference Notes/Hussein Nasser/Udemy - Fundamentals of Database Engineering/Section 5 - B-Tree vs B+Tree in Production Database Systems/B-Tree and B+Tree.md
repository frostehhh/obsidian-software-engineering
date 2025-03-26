---
tags:
  - database
  - reference-notes
  - data-structures
Draft: true
---

# Full Table Scan
- Brute force of searching page per page
- Can be split by having multiple worker threads searching different sections of the data

# B-Tree
- Tree data structure
- Each element is a key-value pair
	- key = index value or tuple
	- Value = pointer to row in heap
- Node = disk page