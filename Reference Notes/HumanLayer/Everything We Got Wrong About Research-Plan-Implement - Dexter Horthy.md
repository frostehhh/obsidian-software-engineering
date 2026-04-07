---
Source: Youtube
Channel:
  - MLOps.Community
tags:
  - reference-notes/video
  - artificial-intelligence/workflow
media_link: https://youtu.be/YwZR6tc7qYg
Draft: false
tier:
  - 0 - Superior
---
# Introduction
## Problem with their initial proposal of specs-only development
- what they got wrong
	- should not read the code
	- claude can have some slop
	- reading long AF plans
- what's better
	- you are the thinker and verifier
## Proper context management
- Staying in the smart zone
- Avoid too many MCPs
- Use prompts for control flow
	- switch case directing to specific context depending on prompt
- referenced [[Writing a good CLAUDE.md]]
- commands
	- `/research_codebase`
	- `/create_plan`
		- work back and forth with me starting with your open questions before outlining the plan
- when researching, for instance `/research_codebase`, be detailed on how to research.
## Issues with [[Understand Spec-driven Development - Kiro, Spec Kit and Tessl#Spec-as-source|spec-as-source]]
- 1000 line plan may be ~= 1000 lines of code
- plans can have surprises
- The code may be different from the plan
- This is a mistake
- Better, read the code. 
- They spent ~6 months not reading the code, only plans. It did not end well.

## Recommendations and Suggestions
- Magic words - work back and forth with me starting with your open questions before outlining the plan
- Models shouldn't have opinions later

# Goals
- leverage planning
- don't outsource thinking
- read the code
- magic words
- human-agent alignment 

# Alternative for Research, Plan, Implement - QRSPI
1. Question
2. Research
3. Design - where we're going
4. Structure Outline - how do we get there, architecture review
5. Plan
6. Worktree
7. Implement
8. Pull Request
## Questions
A phase where questions are generated based on the ticket needed to be done. 
## Research
- keep things objective
- hide ticket from researcher agent
- "Query planning", but for LLMs and reading codebases
- Questions and Research flow must be in separate context windows
- Iterate questions and research phase
## Design
- Depends on Research, Ticket
- Equivalent to sprint planning
- What needs to be done
- Description of the expected outputs
- Involves
	- current state
	- desired end state
	- patterns to follow
- Matt Pocock - The Design Concept?
	- look into this
- Iterate as needed
- Give the agent every opportunity to show you what it's thinking
## Structure Outline
- Depends on Ticket, Research and Design
- equivalent to architecture review
- how do we get there?
- technical designs
- high-level overview of change phases
	- What it's gonna look like
	- What order the phases will be implemented
	- how we're going to test it
	- 
## Plan, Worktree, Implement
- Plan depends on Ticket, Research, Design and Structure Outline
- models love horizontal plans -> database, endpoints, frontend all at the same time
	- ideally, do vertical planning. Make steps small enough that are easy enough to verify in small chunks
- the usual task list and implementation
- spot check the plan
- Save deep review for the actual code
- Testing and verifying
	- he dunno. This is a whole different topic to talk about
	- He referred to Drew Breunig. Can check his article [here](https://www.dbreunig.com/2026/03/04/the-spec-driven-development-triangle.html)

## Pull Request
- Deep review of code by humans
---

# What's next?
- how to measure impact?
- how to eval improvements?
- There will be an upcoming and updated version of this talk on April 20-21, 2026
- ![[Pasted image 20260408022214.png]]

# Personal Thoughts
- I think ideally, we want to make it so that our standards will be automated via agent Skills so that we can give less effort in collaborating with AI
- This can be an openspec schema
# Questions
- Is there an article that shows the context he showed in this video?
- What is question part?
- What is research part?
- How would you do design part?
- How would you do structure part?
- What is query planning?

# See Also
## Articles that discuss the points from the video
https://alexlavaee.me/blog/from-rpi-to-qrspi/ - discussion regarding the video
https://www.heavybit.com/library/article/whats-missing-to-make-ai-agents-mainstream
https://thehumansintheloop.substack.com/p/making-agents-mainstream-for-dev-with-dexter-horthy