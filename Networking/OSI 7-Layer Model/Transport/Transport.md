---
aliases: [Layer 4]
---

- Layer 4 resolves the following issues with [[Network|Layer 3]]
	- when multiple packets sent in a specific order, it can be received in a different order by the destination device.
	- There are no communication channels. IP packets on their own cannot be used to distinguish the intended application at the destination IP
- [[Transmission Control Protocol]] (TCP) and [[User Datagram Protocol]] (UDP) which both run on top of [[Internet Protocol|IP]]