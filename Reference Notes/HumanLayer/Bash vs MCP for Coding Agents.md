---
Source: Youtube
Channel: Boundary
tags:
  - reference-notes/video
media_link: https://youtu.be/RtXpXIY4sLk
source_url: https://github.com/ai-that-works/ai-that-works/tree/main/2025-09-16-coding-agent-tools-bash-vs-mcp
Draft: false
---

### Key Topics Covered
- Token efficiency and the downsides of JSON in tool definitions
- Understanding context windows and their impact on model accuracy
- Writing your own drop-in replacements for MCP tools
- Naming conventions and their critical role in model outputs
- Dynamic context engineering techniques
- Advanced tricks like .shims for forcing uv instead of python or bun instead of npm
- Real-world applications and performance optimizations
- Best practices for using MCPs effectively
# Important takeaways
- MCP context is inserted AFTER the user prompt. As a result, it tends to be not cached in most cases
- There is a lack of control over what MCPs insert into the context
- MCP provides tooling that gives you a quickstart with interacting with tooling
- Bash is more context efficient but may take multiple attempts to get it right
- It is more efficient to create your own scripts to integrate with your LLM usage to have full ownership