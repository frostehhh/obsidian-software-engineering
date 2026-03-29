---
tags:
  - software
  - artificial-intelligence/context-engineering
source_url: https://www.humanlayer.dev/blog/writing-a-good-claude-md
Draft: false
---

# Notes
- Best to be mindful of the contents of the CLAUDE.md file
- Concision is key
- Keep in CLAUDE.md information that is relevant for 90% of tasks in the codebase
- Do progressive disclosure of context for your LLM. Direct to information it can find when it needs to. You can have separate `.md` files that contain more information in case the AI needs context relevant to this
- Linters are expensive. Use lint tools instead. Generally, use deterministic, non-AI tools that can fit your needs
