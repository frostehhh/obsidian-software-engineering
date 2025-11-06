---
Source: Youtube
Channel: Matt Pocock
tags:
  - reference-notes
  - artificial-intelligence
  - artificial-intelligence/claude
  - artificial-intelligence/workflow
  - artificial-intelligence/prompt-engineering
media_link: https://www.youtube.com/watch?v=kZ-zzHVUrO4
Draft: false
---

1. Include in CLAUDE.md instructions to have concision. Shorter generation of messages while easy to comprehend and reducing tokens generated
2. Utilization of plan mode prior to code generation
3. Instructing to make the plan multi-phase
4. Execute each phase one at a time
5. After each execution, review the code manually
6. Proceed with the next stage if good.
7. In case you are nearing the context window limit, use Github CLI or a markdown file to store the current plan state.
8. After clearing the context window, prompt to read the plan and start with the execution of the next phase.