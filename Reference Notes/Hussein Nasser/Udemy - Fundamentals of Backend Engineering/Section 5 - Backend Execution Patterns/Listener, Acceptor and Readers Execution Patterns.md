---
tags:
  - reference-notes
  - backend
Draft: true
"Prev:":
  - "[[The Listener, the Acceptor and the Reader]]"
---

# Single Listener, Acceptor and Reader Thread Execution Pattern
NodeJS
![[Pasted image 20250323230156.png]]
Can spin up new instances of NodeJS if we need more threads.
# Single Listener, Acceptor and Multiple Readers Thread Execution Pattern
Memcached
![[Pasted image 20250323230359.png]]
- Each white circle is a thread


# Single Listener, Acceptor, Reader and Message Load Balancing Execution Pattern
![[Pasted image 20250323231313.png]]
# Multiple Accepter Threads on a Single Socket Execution Pattern
NGINX
![[Pasted image 20250323231929.png]]
Has a locking mechanism so that 1 thread can accept one request at a time

# Multiple Listeners, Acceptors and Readers with Socket Sharding Execution Pattern
![[Pasted image 20250323232437.png]]Sharing socket between multiple processes
OS will distribute processes to threads. Load balancing at OS level
As a result, no competition occurring between threads processing the same request.