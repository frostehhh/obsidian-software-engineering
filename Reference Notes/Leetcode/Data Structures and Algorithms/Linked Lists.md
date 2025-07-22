---
tags:
  - reference-notes
  - pattern
  - algorithms
source_url: https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/704/linked-lists/4506/
---

# Patterns
## Singly Linked List
## Doubly Linked List
## Dummy Header Node
Create a temporary head node that targets that actual head of the linked list. The purpose is to keep track of the first node especially in cases where we want to move the head node to another position

## Reversing Linked Lists
## Slow and fast Traversal
### Finding loops
If there is a slow traversal(+1 each iteration) and a fast traversal(+2 each iteration), it is inevitable that they will land on the same node. If true, there is a loop
### Finding half
