---
tags:
  - software
  - artificial-intelligence
  - artificial-intelligence/context-engineering
  - reference-notes
source_url: https://www.humanlayer.dev/blog/context-efficient-backpressure
Draft: false
tier:
  - 2 - Above Average
---

- Optimize reading of logs for AI
	- Filter out information that is not needed by AI
		- example. timing, etc.
	- Can use tools like grep
- Fail fasts for tests
	- Have AI resolve failing test cases one at a time
- Stay in the context window smart zone -> ~40% or 75k out of 200k(at the time of writing)