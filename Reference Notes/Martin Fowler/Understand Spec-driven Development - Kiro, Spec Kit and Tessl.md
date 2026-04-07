---
tags:
  - reference-notes/article
source_url: https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html
Source:
author: Birgitta Böckeler
Draft: false
---

# What is spec-driven development?
Spec-driven development is a development methodology where we create specs, not code, as the primary artifact of software. This typically includes documents like product requirements document, technical design and tasks document.

Note that different terms for these documents are used interchangeably.

Similar to memory banks, these documents are used as a foundational context during the software development phase. The difference is that memory banks are for general use are to be used across all tasks while specs are tied to development of those specs.

# Implementation Levels
## Spec-first
The specs are created first prior to development of a feature or enhancement
## Spec-anchored
After initial development of a feature, the specs are retained and updated as the feature is developed over time.
## Spec-as-source
The spec documents act as the main artifact in software development.
# Implications of SDD
## Workflow restrictions
- The suggested workflow is too strict and cumbersome. 
- Considering existing SDD Agentic AI tools like Kiro and Github Spec Kit, it is not ideal for simpler tasks as they introduce too much overhead than what is needed to efficiently accomplish the tasks.