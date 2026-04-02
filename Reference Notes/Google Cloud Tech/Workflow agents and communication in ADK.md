---
Source: Youtube
Channel: Google Cloud Tech
tags:
  - video-notes
  - artificial-intelligence
  - artificial-intelligence/agent
media_link: https://www.youtube.com/watch?v=WfJcCeLZD2I&list=PLIivdWyY5sqLNeW9MPxldbbevMEJGMWBG&index=8
Draft: false
---

# Types of agents by workflow
- sequential - run in a fixed order
- parallel - agents are run in parallel
- loop - a group of agents are executed in a loop until specified success conditions are met

# Communication
- Shared session state - global state shared to all subagents
	- Can be thought of a central document or root source of truth
- Delegator
	- Usually called orchestrator
	- Root agent responsible for delegating tasks to subagents
- Execution as a tool
	- Invoke an agent as a tool
	- Can be `AgentTool`
