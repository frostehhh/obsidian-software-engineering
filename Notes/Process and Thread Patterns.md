---
tags:
  - notes
  - operating-system
Draft: false
related-reference-note:: d

"Parent:":


---

## Single-Threaded Process
- A process with one thread
- Example: NodeJS

## Multi-processes
- Takes up more memory but isolated
- Can utilize multiple cores in CPU
- Example: NGINX

# Multi-threaded Process
- Can utilize multiple cores in CPU
- A single process contains multiple threads sharing the same memory
- There can be race conditions among the threads(competing)
- Example: SQL
	- **Locks and Latches issue**. There is