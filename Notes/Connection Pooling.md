---
tags:
  - networking
  - notes
Draft: false
related-reference-note:: [[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Backend Engineering/Section 2 - Backend Communication Design Patterns/Multiplexing and Demultiplexing|Multiplexing and Demultiplexing]]
---

Connection pooling is a method of maintaining active connection states that can be reused for multiple different independent requests.

See the example below. The incoming requests can be seen as many multiple connections. These are demultiplexed into 4 database connections in the backend.

![[ConnectionPooling.png]]