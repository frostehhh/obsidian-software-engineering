---
tags:
  - notes
  - aws/ses
Draft: true
Parent:: 
  - "[[Simple Email Service|AWS SES]]"
---

# Prerequisites
- Configure DNS records to prove ownership
- Configure MX record to identify mail server to use
- Authorization configuration to allow receipt ruleset action execution

# Receiving
Configure Receipt rulesets, which consist of
- condition - prerequisite for executing action
- action - invoke other AWS services. Ex. [[Lambda]]

# References
https://docs.aws.amazon.com/ses/latest/dg/receiving-email-concepts.html
