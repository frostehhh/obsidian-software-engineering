---
tags:
  - notes
  - backend
Draft: false
related-reference-note:: 
- "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Backend Engineering/Section 5 - Backend Execution Patterns/Backend Idempotency|Backend Idempotency]]"
---

- Idempotency means that a request does the same thing every time it is executed.
- For example we have a POST /postcomment endpoint, every time we send a request to this, a new record gets added to the corresponding database table. **This is not idempotent**
- We can implement idempotency by simply considering a requestId/idempotency token. When the backend knows that a requestId has been processed, it will do nothing.
	- Another example is using upserts(update/insert actions)
