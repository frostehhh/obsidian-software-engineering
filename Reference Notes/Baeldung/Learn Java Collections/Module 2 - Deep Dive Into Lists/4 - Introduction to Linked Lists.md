---
tags:
  - reference-notes
  - java/collections/list
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-4-introduction-to-linkedlists
Draft: false
---

- Uses `Deque` [[First-In First-Out]] 
- For stack [[Last-In First-Out|LIFO]], `push` and `pop`
- For queue, `offer`, `offerFirst`, `offerLast`, and `poll`, `pollFirst` and `pollLast`.
- For retrieving without removing:
	- peek
	- peekFirst
	- peekLast

# Benefits
- Efficient insertion in middle of list due to updating only pointer references
- Memory-efficient relative to [[1 - Introduction to ArrayLists|ArrayLists]], which initializes memory for data storage based on given capacity.
# Weaknesses
- Slow random access reads with index accessors
