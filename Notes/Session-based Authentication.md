---
tags:
  - notes
  - security/authentication
Draft: false
"related-reference-note:":
  - "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Backend Engineering/Section 7 - Extras/JSON Web Token]]"
---

An authentication method where after a user is initially authenticated via login, a `sessionId` is persisted in a database and the sessionId is returned to the user as a response to the login request.

# Flow
On successful login, return a sessionID.
![[Session-based Authentication 2025-03-24 20.15.27.excalidraw]]

In every request, this sessionID is passed to authenticate the user.
When a user sends a request with a sessionID, the load balancer passes the request to one of the servers and the receiving server will check if the sessionID exists in the database.

# Cons
- Extra hop due to having to query database for existence of sessionID

