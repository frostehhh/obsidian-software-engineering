---
tags:
  - guide
  - artificial-intelligence/workflow
  - notes
  - artificial-intelligence/context-engineering
source_url: https://www.humanlayer.dev/blog/stop-claude-from-ignoring-your-claude-md
tier:
  - 1 - High
---

Use this block in your context if you want to add conditional instructions

```
<important if="you are writing or modifying tests">
- Use `createTestApp()` helper for integration tests
- Mock database with `dbMock` from `packages/db/test`
- Test fixtures live in `__fixtures__/` directories
</important>
```

