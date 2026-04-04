---
tags:
  - software
  - artificial-intelligence/harness-engineering
  - reference-notes
source_url: https://www.humanlayer.dev/blog/skill-issue-harness-engineering-for-coding-agents
Draft: false
has-questions: false
tier:
  - 1 - High
---

# Summary
This article provides a cohesive overview of harness engineering for coding agents. It provides highly informative information on how to configure different aspects in an agentic workflow
# CLAUDE.md
- Simple rule of thumb is max 60 lines
- Avoid context rot. A lot of auto-generated CLAUDE.md, AGENTS.md and other similar files are unhelpful
- It is more productive to mindfully construct a cohesive base context document
# MCP
- every prompt, the agentic AI evaluates it against an MCP's description to decide whether it needs to use the MCP.
- Given this, remove MCPs that you don't use or rarely use. Enable only when needed
- If you can optimize such that you can convert your MCP usage to a simpler CLI tool, do so
# Skills and Tools
- For reusable knowledge and/or tools
- Can be used for progressive disclosure
- Skills can be used to progressively disclose other `.md` files as well
# Subagents
- Used primarily to avoid context rot
- Can keep the main session to use Opus
- Subagents can opt to use Sonnet, Haiku or cheap AI models

## Common Usecases
- exploring implementation patterns
- Exploring the codebase repository
- Checking logs

# Hooks
- Lifecycle hooks
- used as a means of triggering actions based on specified conditions

# Conclusion
- Starting simple and adding configuration only when the agent actually failed
- Designing, testing, iterating — and throwing away things that didn’t help. I have thrown away many more hooks than we actually use today.
- Distributing battle-tested configurations to the whole team via repository-level config
- Optimizing for iteration speed, not "likelihood of 1-shotting it on the first attempt"
- Giving the agent a set of capabilities (Linear) and then carefully paring down what we exposed to the model once we knew what we needed.

# See Also
https://openai.com/index/harness-engineering/
https://www.aihero.dev/a-complete-guide-to-agents-md

# OpenAI Harness Engineering
## Example on directory structure for documentation for AI 
```
AGENTS.md
ARCHITECTURE.md
docs/
├── design-docs/
│   ├── index.md
│   ├── core-beliefs.md
│   └── ...
├── exec-plans/
│   ├── active/
│   ├── completed/
│   └── tech-debt-tracker.md
├── generated/
│   └── db-schema.md
├── product-specs/
│   ├── index.md
│   ├── new-user-onboarding.md
│   └── ...
├── references/
│   ├── design-system-reference-llms.txt
│   ├── nixpacks-llms.txt
│   ├── uv-llms.txt
│   └── ...
├── DESIGN.md
├── FRONTEND.md
├── PLANS.md
├── PRODUCT_SENSE.md
├── QUALITY_SCORE.md
├── RELIABILITY.md
└── SECURITY.md
```

# Questions
- What subagents would I need?
	- I think one way to figure this one out is observe tasks that can be separated into a subagent
		- Perhaps tasks that consume a lot of context
		- Start simple
		- Complexify if needed to stay within the [[Claude Models Smart Zone]- 