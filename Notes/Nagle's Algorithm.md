---
tags:
  - backend
  - notes
Draft: false
related-reference-note:: 
- "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Backend Engineering/Section 5 - Backend Execution Patterns/Nagle's Algorithm|Nagle's Algorithm]]"
---

Delay in the client side

- Sender waits to send an packet until:
	- a packet is at the maximum segment size(MSS) to avoid wasted bandwidth when possible. 
	- An ACK is received relating the previously sent packets
- If there is no more data to send, it just sends.
- The delay this algorithm causes tends to be undesirable and people may prefer performance over bandwidth efficiency.
- In curl cli, TCP_NODELAY was enabled by default and it is related to this algorithm.
