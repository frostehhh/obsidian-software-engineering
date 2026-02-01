---
tags:
  - reference-notes
  - java/collections
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-2-overview-of-the-java-collections-framework
Draft: false
---

- Collections Framework
	- Collections
		- List
		- Set
		- Queue
	- Map
- The standard Collections objects are not thread-safe by default
	- There are thread-safe implementations(not discussed in this article yet)

# List
Ordered collections accessible by index
## Types
- ArrayList
- LinkedList

# Set
Unique collections
## Types
- HashSet - efficient lookups by hashing
- TreeSet - preserve set order by comparator
- LinkedHashSet - insertion order is preserved
# Queue
- Queue - typically, but not necessarily [[First-In First-Out|FIFO]]
	- Deque
		- LinkedList
		- ArrayDeque
	- PriorityQueue
		- limited number of elements
		- If will exceed max size, elements of highest priority are removed first
		- Ordered by value
		
# Map
- HashMap - default go-to for accessing objects by key
- LinkedHashMap - insertion order is preserved
- TreeMap - objects are sorted by key

|Type|Class/Interface|Ordered?|Duplicates Allowed?|Key Features / Use Cases|
|---|---|---|---|---|
|_List_|_List_|Yes|Yes|Ordered collection, allows random access and duplicates|
||_ArrayList_|Yes (by index)|Yes|Fast random access, good for read-heavy operations|
||_LinkedList_|Yes (by index)|Yes|Fast insertions/removals, also implements _Deque_|
|_Set_|_Set_|Depending on implementations|No|Unique elements, no duplicates allowed|
||_HashSet_|No (unordered)|No|Fast lookup, no order guarantee|
||_LinkedHashSet_|Yes (insertion)|No|Maintains insertion order|
||_TreeSet_|Yes (sorted)|No|Sorted elements using natural/comparator order|
|_Queue_|_Queue_|Yes|Yes|Holds elements before processing, typically FIFO|
||_Deque_|Yes (double-ended)|Yes|Add/remove elements at both ends, for FIFO and LIFO|
||_ArrayDeque_|Yes (insertion)|Yes|Resizable array-based, faster than _LinkedList_ in most cases|
||_PriorityQueue_|No|Yes|Elements can be obtained by priority, not FIFO|
|_Map_|_Map_|Depending on implementations|No duplicate keys|Key-value pairs, keys must be unique|
||_HashMap_|No|No duplicate keys|Fast lookup, no ordering|
||_LinkedHashMap_|Yes (insertion)|No duplicate keys|Maintains insertion order|
||_TreeMap_|Yes (sorted by key)|No duplicate keys|Keep keys sorted|
