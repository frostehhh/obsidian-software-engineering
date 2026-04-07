---
tags:
  - guide
  - artificial-intelligence/workflow
  - notes
  - setup
  - artificial-intelligence/setup
  - artificial-intelligence/open-spec
Draft: false
---
# Source
https://github.com/Fission-AI/OpenSpec
# Instructions
## Installing OpenSpec
```shell
npm install -g @fission-ai/openspec@latest

cd your-project
openspec init
```

## Configuring Openspec
Configure OpenSpec according to preferred workflows and delivery. Workflows refer to available commands. Delivery refers to what is installed: skills or commands or both.
```
openspec config profile
```

## Creating Schema
Schemas are templated workflows that can be created and customized as needed.

```
// Create new schema via interactive mode
openspec schema init sample-schema
```

See recommended schemas in 
# References
https://github.com/Fission-AI/OpenSpec/blob/main/docs/workflows.md

# See Also
Note that as of 2026-04-08, the openspec directory name is hardcoded. It is not configurable.
[Feature Request - Allow configurable OpenSpec directory name #581](https://github.com/Fission-AI/OpenSpec/issues/581)

