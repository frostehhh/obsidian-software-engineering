---
tags:
 - database
 - notes
 - data-structures 
related-reference-note:: 
- "[[B-Tree and B+Tree]]"
---

# B-Tree
- Self-balancing tree
- NOT Binary search tree. This is a different concept
- Left child nodes are smaller values while right child nodes are larger values
- Each node can have minimum 2 elements and max 4 elements(4 is the degree. Can be changed. Minimum is always half). Root node is an exception
- Node has elements
- Node - root node, internal node, leaf node
- Node = disk page
- Each element is a key-value pair

## Example
![[Pasted image 20250327004013.png]]

## Limitations
![[Pasted image 20250327004935.png]]

# B+ Tree
- keys = only internal nodes = more keys
- values = only leaf nodes
- leaf nodes = key + value
- leaf nodes are "linked" and allows traversal
- Good for range queries due to less steps needed
## Example
![[Pasted image 20250327010218.png]]
## DBMS Considerations
![[Pasted image 20250327010418.png]]
## Storage cost in Postgres vs MySQL
![[Pasted image 20250327010441.png]]
# References
[Understanding B-Trees: The Data Structure Behind Modern Databases](https://www.youtube.com/watch?v=K1a2Bk8NrYQ)
https://en.wikipedia.org/wiki/B-tree
https://en.wikipedia.org/wiki/B%2B_tree