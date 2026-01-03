---
tags:
  - notes
Draft: true
Friend:: 
- "[[Mutex]]"
- "[[Semaphore]]"
---

|Mutex|Semaphore|
|---|---|
|A mutex is an object.|A semaphore is an integer.|
|Mutex works upon the locking mechanism.|Semaphore uses signaling mechanism.|
|Operations on mutex: Lock & Unlock|Operation on semaphore: Wait & Signal|
|Mutex does not have any subtypes.|Semaphore is of two types: Counting Semaphore & Binary Semaphore|
|A mutex can only be modified by the process that is requesting or releasing a resource.|Semaphore work with two atomic operations (Wait, signal) which can modify it.|
|If the mutex is locked then the process needs to wait in the process queue and mutex can only be accessed once the lock is released.|If the process needs a resource and no resource is free. So, the process needs to perform a wait operation until the semaphore value is greater than zero.|
# References
https://www.geeksforgeeks.org/operating-systems/mutex-vs-semaphore/