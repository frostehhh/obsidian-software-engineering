---
tags:
  - reference-notes
  - backend
  - networking/communication
  - operating-system
Draft: false
---

# How the Backend Accepts Connections
1. Server's Kernel creates a socket for handling connections and **SYN queue** and an **Accept queue**
2. Client sends a SYN to the server
3. Server adds to a SYN queue
4. Server sends back a SYN/ACK
5. Client receives the SYN/ACK
6. Client sends a SYN
7. Server Kernel receives the SYN, removes the SYN from the SYN queue and then adds an entry to the accept queue
8. Server Backend completes the connection and removes it from the accept queue
9. A file descriptor is created for the connection

# Problems with accepting connections
Backend is slow
SYN flooding - when clients send SYN but don't ACK