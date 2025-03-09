---
tags:
  - course-notes
  - backend
Draft: true
---

synchronous definition
# Synchronous
- Tasks are coordinated
- Caller cannot work while waiting for a response
- Assuming there are 2 processes A and B, A will process a task, and pass a request to B. While B is processing, A is blocked is left to wait with nothing to do.
- Also called blocking

# Asynchronous
- Tasks do not need to be coordinated
- Caller can work while waiting for a response
- For a caller to know if the receiver is done processing, we can do the following approaches:
	- Polling
	- Receiver will callback the caller
	- Alternatively, the main process can create a new thread to run an async process

# Synchronous vs Asynchronous in request response

# Synchronous vs asynchronous in real life

Synchronous example is when you are having a communication with someone face to face
Asynchronous is email communication.

# Asynchronous workload is everywhere

- Asynchronous programming(promises/features)
- Asynchronous backend processing
- Asynchronous commits in postgres
- Asynchronous IO in Linux (epoll, io_uring)
- Asynchronous replication
- Asynchronous OS fsync (fs cache)


