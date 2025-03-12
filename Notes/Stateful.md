---
tags:
  - notes
  - backend
Draft: false
opposite:: [[Stateless]]
related:: [[Stateless vs Stateful]]
---

- A stateful entity stores state within it
- When state is lost, workflow breaks
- The entity must not be restarted to avoid breaking client workflows
- State-dependent
# Example
Assume there is a client, a server and a database. The client logs in to the server via a request and is returned a response that contains a cookie containing a session ID. A state is stored in the **server** containing the client's session ID. When the server restarts, it's local cache is cleared and the client session is gone.

![[Stateful Backend.png]]