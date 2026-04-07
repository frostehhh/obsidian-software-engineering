---
Source: Youtube
Channel:
  - MLOps.Community
tags:
  - reference-notes/video
  - artificial-intelligence/workflow
media_link: https://youtu.be/YwZR6tc7qYg
Draft: true
---

# Draft
- community uses their prompts from humanlayer repository
- RPI - research plan implement as suggested from claude code best practices
- what's they got wrong
	- should not read the code
	- claude can have some slop
	- reading long AF plans
- what's better
	- you are the thinker and verifier
- commands
	- `/research_codebase`
	- `/create_plan`
		- work back and forth with me starting with your open questions before outlining the plan
- when researching, for instance `/research_codebase`, be detailed on how to research.
- models shouldn't have opinions later
- experts vs mediocre
	- experts say the magic words -> work back and forth with me
- referenced [[Writing a good CLAUDE.md]]
- advocated for reading the plans as output
	- 1000 line plan may be ~= 1000 lines of code
	- plans can have surprises
	- The code may be different from the plan
	- This is a mistake
	- Better, read the code. 
	- They spent ~6 months not reading the code, only plans. It did not end well.
- PLEASE READ YOUR CODE. I'M BEGGING YOU
- Shoot for 2-3x whil realistically
# Goals
- leverage planning
- don't outsource thinking
- read the code
- magic words
# Better Research
- keep things objective
- hide ticket from researcher agent
- query planning

---
- the dumb zone. already referenced in his previous talks
- too many MCPs
- prompts for control flow
	- switch case directing to specific context depending on prompt
# Alternative for Research, Plan, Implement
1. Question
2. Research
3. Design - where we're going
4. Structure Outline - how do we get there, architecture review
5. Plan
6. Worktree
7. Implement
8. Pull Request

---
- mind your instruction budget
- Research patterns to follow
- Matt Pocock - The Design Concept?
	- look into this
- goal is human-agent alignment
- structure outline = leverage
- models love horizontal plans -> database, endpoints, frontend all at the same time
	- ideally, do vertical + micro planning
- plan, implement
	- the usual task list and implementation
	- spot check the plan
	- Save deep review for the actual code
- Testing and verifying
	- he dunno. This is a whole different topic to talk about
# What's next?
- how to measure impact?
- how to eval improvements?
- There will be an upcoming and updated version of this talk on April 20-21, 2026
- ![[Pasted image 20260408022214.png]]

# Questions
- Is there an article that shows the context he showed in this video?

# See Also
## Articles that discuss the points from the video
https://alexlavaee.me/blog/from-rpi-to-qrspi/ - discussion regarding the video
https://www.heavybit.com/library/article/whats-missing-to-make-ai-agents-mainstream
https://thehumansintheloop.substack.com/p/making-agents-mainstream-for-dev-with-dexter-horthy