---
date: 2026-02-05T17:52
---

# Outline
- ArrayList bulk operations
- LinkedList
- Iterators

# ArrayList bulk operations
- utility functions optimized for bulk operations

## Operations
- addAll(Collection)
- addAll(index, Collection)
- removeAll(Collection)
- removeIf(Predicate)
- update?

# LinkedList
- implements List and Deque
- supports index access
- Deque
	- poll - remove and return
	- pollFirst
	- pollLast
	- peek - retrive only
	- peekFirst
	- peekLast
	- offer - push to end
	- offerFirst - push to front
	- offerLast - push to end
	- push
	- pop

# Iterables and Iterator
- not all collections support this
- supports adding and/or removing of elements during iteration
## Iterator
- next
- hasNext
- remove
- forEachRemaining
## ListIterator
- extends Iterator
- Can iterate in reverse
- add
- set

## Iterable.forEach