---
tags:
  - notes
  - programming-languages/kotlin
Draft: false
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
- launch
	- coroutine builder
	- Executes and does not return
- async
	- coroutine builder
	- executes and returns result
- runBlocking
	- coroutine scope builder
	- blocks underlying thread
	- creates new coroutine
- coroutineScope
	- coroutine scope builder
	- suspending function
	- does not create new coroutine
- delay - suspending function
- `suspend` keyword - include before `fun` declaration to create a suspending function

# References
https://kotlinlang.org/docs/coroutines-guide.html

# Questions
