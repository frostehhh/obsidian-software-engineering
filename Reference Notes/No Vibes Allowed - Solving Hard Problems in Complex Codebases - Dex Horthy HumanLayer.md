---
Source: Youtube
Channel:
tags:
  - video-notes
  - software
  - artificial-intelligence
  - artificial-intelligence/workflow
media_link: https://www.youtube.com/watch?v=rmvDxxNubIg
Draft: true
---

# Key takeaways
- Goals in AI driven development
	- ...
- 
- Spec-driven development(SDD) as a term is ambiguous. It is not clear what is meant by it really since it has been adapted in different forms
	- The key is proper context management and providing only enough context that the AI would need to accomplish the goals
- Simply
	- Research -> Plan -> Implement
	- Research
		- understand how the system works
		- find the right files
		- stay objective
	- Plan
		- Detailed implementation steps
		- specific code changes -> files and lines
		- Explicit testing plan
		- Planning prompt example
			![[Pasted image 20260308225527.png]]
	- Implement
		- go write the code
- context control is key
- agents are meant to create a fork of the current context and to be used as a separate task for more efficient context management
- For agent usage, context steering documents are fine if seldomly changed. For instance, if they are placed at the root of a repository.
	- If there are steering documents per module or child module, they will need to be updated for each related code change. This however is prone to becoming outdated especially for deeply nested modules
	- For a reliable approach on codebase analysis, use an agent to explore a module or multiple modules.
- Code review is for mental alignment
	- In the merge request description, describe the plan to make it much easier for the code reviewers.
	- If there is a bad part of the plan, there is bad code. 1 section of a bad plan is relatively easier to read compared to significantly more lines of code. Ultimately, this makes the review process more efficient
	- The code reviewer can more easily be onboarded with the merge request changes.
- Figuring out how to manage context for a task will take reps


# Continue Reading
https://www.humanlayer.dev/blog/advanced-context-engineering