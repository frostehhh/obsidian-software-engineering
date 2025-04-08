---
tags:
  - notes
  - programming-languages/javascript
---

1. What is an event loop
	[https://www.youtube.com/watch?v=8aGhZQkoFbQ](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
	An event loop is a runtime model that describes how JavaScript executes code.
	### Heap
	Simply where memory is allocated
	
	### Call Stack

	It’s used by Javascript to keep track of what the current execution context is. This can be seen when you see errors in console. Each function or block has its own execution context
	
	### WebAPIs
	
	JavaScript runs things on thing at a time, but in a browser environment, we are given access to Web APIs. These are executed like separate threads, which means that these code can run simultaneously with your regular JavaScript code.
	
	### Task Queue
	
	This is a queue that contains callbacks for asynchronous tasks that have completed, and are ready to be executed by JS. Items in this queue are processed only when the call stack is empty, and they are pushed onto the call stack for processing.