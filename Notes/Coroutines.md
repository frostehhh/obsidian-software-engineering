---
tags:
  - notes
  - programming-languages/kotlin
Draft: true
source_url:
aliases:
 - Kotlin Coroutines
---

- Coroutines are suspendable functions stored in memory
- Scheduled to be processed by [[Thread]]s. They don't live in threads
- Stores state in memory
	- Line to continue from
	- Containing Variable values
	- 3 state types - running, suspended, completed
	- External variable values captured within the coroutine scope
- Dispatchers - scheduling mechanism for coroutines to allocate to threads
	- Default
	- IO
	- ...

# References
https://kotlinlang.org/docs/coroutines-guide.html