---
aliases: [Layer 4]
---

# Summary
Layer 4, the transport layer, is <mark style="background: #FFF3A3A6;">responsible for ensuring that data is delivered reliably and efficiently from one device to another</mark>. It does this by establishing connections between applications on different devices, and managing flow control and error recovery. This layer defines two main protocols: the [[Transmission Control Protocol]] (TCP) and the [[User Datagram Protocol]] (UDP). In this lesson, we will explore the functions and protocols of Layer 4 in detail to understand how it enables reliable end-to-end communication between devices.

# More Info

- Layer 4 resolves the following issues with [[Network|Layer 3]]
	- when multiple packets sent in a specific order, it can be received in a different order by the destination device.
	- There are no communication channels. IP packets on their own cannot be used to distinguish the intended application at the destination IP
- [[Transmission Control Protocol]] (TCP) and [[User Datagram Protocol]] (UDP) which both run on top of [[Internet Protocol|IP]]