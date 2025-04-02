---
tags:
  - notes
  - backend
  - backend/communication
Draft: false
"similar:":
  - "[[Notes/Push]]"
has-questions: true
---

# Server Sent Events
A communication method where a stream is initiated between a client and a server where they communicate unidirectionally. The communication channel is maintained for the server to send updates to the client in real time.
- Unidirectional communication where server send messages to the client

# Pros
- real time
# Cons
- Server has no knowledge of client's capabilities of receiving x number of pushes
	- In this case, long polling is better for lighter clients
- Client must be connected
- Limit when using HTTP/1.1. max 6 connections

# Questions
What is the difference with [[Notes/Push|Push]]?

Why is it unidirectional?


