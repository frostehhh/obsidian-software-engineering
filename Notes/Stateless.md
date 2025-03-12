---
tags:
  - notes
  - backend
Draft: false
opposite:: [[Stateful]]
related:: [[Stateless vs Stateful]]
---

- A stateless entity does not store any state within it
- It can rely on state that is stored elsewhere, and it is usually non-breaking incident when state is lost.
- The entity can be restarted without breaking a client's workflow
- Client is responsible for storing state and including state in requests to the backend
# Example
Assume there is a client, a server and a database. The client logs in to the server via a request and is returned a response that contains a cookie containing a session ID. A state is stored in the **database** containing the client's session ID. When the server restarts, it's local cache is cleared, but this is not an issue since the session ID is persisted in the database.

![[Stateless Backend.png]]