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
- Binary search tree
- Left child nodes are smaller values while right child nodes are larger values
- Each node can have minimum 2 elements and max 4 elements(4 is the degree. Can be changed. Minimum is always half). Root node is an exception
- Node has elements
- Node = disk page
- Each element is a key-value pair

## Example
![[Pasted image 20250327004013.png]]

# Limitations

# References
[Understanding B-Trees: The Data Structure Behind Modern Databases](https://www.youtube.com/watch?v=K1a2Bk8NrYQ)
https://en.wikipedia.org/wiki/B-tree
https://en.wikipedia.org/wiki/B%2B_tree