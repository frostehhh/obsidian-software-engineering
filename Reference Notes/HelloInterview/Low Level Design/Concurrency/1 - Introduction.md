---
tags:
  - low-level-design
  - reference-notes
  - synchronization
  - concurrency
  - computer-science/locks
Draft: false
source_url: https://www.hellointerview.com/learn/low-level-design/concurrency/intro
---

# Concurrency 
Concurrency is not a common requirement given to low-level design interviews. However, it may be added when additional requirements are requested. 

Concurrency becomes an issue when there can be multiple threads that can work on the same data within memory. This is because multiple threads can work on the same memory at the same time

# Toolbox
## Atomics
Thread-safe operations on individual variables
## Locks (Mutex)
See [[Mutex]]
## Semaphore
Practically, for limiting number of concurrent processes working on the same lock
See [[Semaphore]]
## Conditionals
- Used together with [[#Locks (Mutex)]]
- If a given condition is false, prompt the current thread to wait and sleep. This will let the other threads proceed with the same lock
## Blocking Queue
Blocking queues combine a queue with condition variables to provide thread-safe producer-consumer handoff. Producers call put() to add items; if full, they block. Consumers call take() to remove items; if empty, they block.