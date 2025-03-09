---
tags:
  - notes
  - computer-science
Draft: false
opposite:: [[Asynchronous]]
---

- Tasks are coordinated
- Caller cannot work while waiting for a response
- Assuming there are 2 processes A and B, A will process a task, and pass a request to B. While B is processing, A is blocked is left to wait with nothing to do.
- Also called blocking