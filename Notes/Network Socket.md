---
tags:
  - notes
  - backend/communication
  - backend/networking
Draft: false
aliases:
  - Internet Socket
"Parent:": "[[Notes/Internet Protocol|Internet Protocol]]"
"Friend:": "[[Network Interface]]"
---

- A socket can be described as an endpoint in a two-way communication channel[^1]. 
- It is a software construct, a logical object that contains an IP Address, Protocol and Port[^2]
- It is a file descriptor
- It works on top of [[Network Interface]]s
	- One [[Network Interface]] : many [[Network Socket]]

[^1]: https://www.ibm.com/docs/en/zos/3.1.0?topic=ncuuss-what-is-socket
[^2]: https://en.wikipedia.org/wiki/Network_socket
