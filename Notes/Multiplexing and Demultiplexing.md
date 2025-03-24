---
tags:
  - notes
  - networking
Draft: false
related:: [[Connection Pooling]]
---

# Multiplexing
Multiple incoming connections to a server are converted into 1 bundled connection
- Results to higher throughput via the bundled connection
- Receiver of bundled connection will require more resources to process the requests

# Demultiplexing
A single incoming connection where different independent requests involved are unbundled into multiple connections equal to the number of requests.
- Results to lower throughput via the debundled connection
- Receiver of bundled connection will require less resources to process the request.

# Examples
![[Multiplexing example HTTP2.png]]![[Multiplexing HTTP2 on the backend.png]]