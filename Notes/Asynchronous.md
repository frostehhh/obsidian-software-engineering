---
tags:
  - notes
  - computer-science
Draft: false
"opposite:": "[[Synchronous]]"
---
- Tasks do not need to be coordinated
- Caller can work while waiting for a response
- For a caller to know if the receiver is done processing, we can do the following approaches:
	- Polling
	- Receiver will callback the caller
	- Alternatively, the main process can create a new thread to run an async process