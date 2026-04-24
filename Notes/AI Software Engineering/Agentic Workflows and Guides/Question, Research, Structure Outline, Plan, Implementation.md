---
aliases: QRSPI
tags:
  - guide
  - artificial-intelligence/workflow
  - notes
Draft: true
source:: 
 - "[[Everything We Got Wrong About Research-Plan-Implement - Dexter Horthy]]"
---

# Issues Encountered with QRSPI OpenSpec schema
- On prompt to create a new OpenSpec spec with a description of the task, the query already did an initial research prior to reaching the `questions` artifact.
- In the `questions` artifact, the questions produced are sometimes not focused on researching the code. There are questions that may not be resolved by exploring the codebase.
	- On second thought, this may be fine since it is not guaranteed that these may not aid code exploration

# References
[[Everything We Got Wrong About Research-Plan-Implement - Dexter Horthy]]
[Comparison of RPI Agentic AI Harnesses ](https://notebooklm.google.com/notebook/a91bf552-99f2-4136-9e87-f0df2456415a)

# References to Explore(DONE)
https://github.com/addyosmani/agent-skills
https://github.com/obra/superpowers
https://github.com/gsd-build/get-shit-done/tree/main
https://github.com/affaan-m/everything-claude-code

As of <u>2026-04-20 00:07</u>, seems that what I can refer from above are the following:
- superpowers brainstorming https://github.com/obra/superpowers/blob/main/skills/brainstorming/SKILL.md
- https://github.com/addyosmani/agent-skills/blob/44dac80216da709913fb410f632a65547866346f/skills/incremental-implementation/SKILL.md#L4
- and humanlayer itself

> [!note]
> I elaborated the components related to research, planning and implementation below. This is so that I can find ways to improve the workflow as I need

# How to go about exploring this
- Understanding the basic needs of the plan - why we're doing research, plan and implement in the first place
- Systems thinking - think about how to efficiently navigate this
- Create a synthesis of different approaches to this process. For example, the different ways of how research can be done

# Output Component Characteristics to Note
- Granularity - high-level vs low-level

# Workflows
## Different Types of Workflows
- Feature creation
	- new implementation
	- new implementation with refactoring of existing code
## Workflow Phases
- Questions
- Research
- Plan
- Implementation
- Validation and Testing
	- Verification Gates
- Review
	- Quality review
	- Human code review
# Input Components
- Source Code
- Problem/Task/Ticket
# Output Components
- Exploration docs of source code
	- Existing code
	- Code components
	- Infrastructure components
	- Libraries
	- Packages used
	- Patterns used
	- Features
	- Utilities
- Product requirements
	- functional requirements
	- non-functional requirements
- Technical references
	- documentation to tools, libraries and frameworks to use
	- Validation of pattern to use
- Technical design
	- Technical components to use
		- database
		- frontend
		- endpoints
		- infrastructure
		- ci/cd pipelines
		- tools
- Implementation plan
	- To-do list
	- Implementation phase
# Exploration Tools
- Researching
- Challenging current design
- Explorative inquiry
	- Brainstorming
- Planning of how to produce an output
	- Produce guidelines and questions in exploring a codebase implementation

# Diagram

![[Question, Research, Structure Outline, Plan, Implementation 2026-04-17 23.45.20.excalidraw]]
# Commands, Skill, Agents that I can reference from other Repos

| Command Functionality           | **get-shit-done** (GSD)        | **superpowers**                  | **agent-skills**                       | **everything-claude-code** (ECC)             |
| ------------------------------- | ------------------------------ | -------------------------------- | -------------------------------------- | -------------------------------------------- |
| ==**Codebase Exploration**==    | `/gsd-map-codebase`,           | n/a (Auto-triggered at start)    | n/a                                    | `explorer` agent,                            |
| ==**Project/Spec Definition**== | `/gsd-new-project`,            | `brainstorming` skill,           | `/spec`; `spec-driven-development`     | `/ecc:plan`; `deep-research`                 |
| ==**Task Planning**==           | `/gsd-plan-phase`,             | `writing-plans` skill,           | `/plan`; `planning-and-task-breakdown` | `/multi-plan`,; `strategic-compact`          |
| **Core Implementation**         | `/gsd-execute-phase`,          | `executing-plans` skill,         | `/build`; `incremental-implementation` | `/multi-execute`,; `verification-loop`       |
| **Test-Driven Dev (TDD)**       | n/a (Built into XML plans)     | `test-driven-development`,       | `/test`; `test-driven-development`     | `/tdd`; `tdd-workflow`                       |
| **Code Review**                 | `/gsd-review`                  | `requesting-code-review`,        | `/review`; `code-review-and-quality`   | `/code-review`,; `typescript-reviewer`       |
| **Security Review**             | `/gsd-secure-phase`,           | n/a                              | `security-and-hardening`               | `/security-scan`,; `security-review`         |
| ==**Debugging**==               | `/gsd-debug`                   | `systematic-debugging`           | `debugging-and-error-recovery`         | `/build-fix`,; `pytorch-build-resolver`      |
| **Deployment/Shipping**         | `/gsd-ship`,                   | `finishing-a-development-branch` | `/ship`; `shipping-and-launch`         | n/a                                          |
| **Parallel Execution**          | `Wave Execution`,              | `dispatching-parallel-agents`    | n/a                                    | `/pm2`,; `/multi-workflow`                   |
| **Quick/Ad-hoc Tasks**          | `/gsd-quick`,                  | n/a (Mandatory workflow)         | n/a                                    | `/gsd-fast` (OpenCode shim)                  |
| **Context Management**          | `CONTEXT.md`,                  | `using-git-worktrees`            | `context-engineering`                  | `/compact`; `/clear`; `/model-route`         |
| ==**Discovery/Experiments**==   | `/gsd-spike`,                  | `brainstorming`                  | `idea-refine`                          | `exa-search`; `documentation-lookup`         |
| **Learning/Improvement**        | `/learn`                       | `writing-skills`                 | n/a                                    | `/instinct-import`; `/evolve`                |
| **Project UI Design**           | `/gsd-ui-phase`; `/gsd-sketch` | n/a                              | `frontend-ui-engineering`              | `frontend-slides`; `remotion-video-creation` |
|                                 |                                |                                  |                                        |                                              |
