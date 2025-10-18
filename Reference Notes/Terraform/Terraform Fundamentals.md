---
tags:
  - reference-notes
  - terraform
  - infrastructure
  - infrastructure-as-code
Draft: true
---

# Building Blocks
- provider
- data
- resource
- terraform
- locals - overriding variables in the current file
- variable
- moving - for moving infrastructure to another location(ex. module A to module B) while persisting the existing identifiers, variables associated with it.
# Workspaces
- CLI feature for terraform deployments that differ by variables only. For example: dev, staging, prod deployments
# Modules
- Reusable groups of configuration
- Simplifies redeclaration of similar configuration
- Abstracts configuration for simplicity and ease of development and maintenance
## Module Creation Pattern
- Group modules by volatility and purpose
- Group closely related components into a module
- Start with MVP for modules. Add more complexity gradually as time goes on.
- Example modules
	- Web
	- Database - Postgresql
	- App
	- Routing
	- Security - IAM

# Testing

## Check blocks
For checking validity of infrastructure itself
## Lifecycle Checks
Precondition and postcondition
For checking validity of infrastructure itself

## Run Tests
- Run blocks
- for testing behavior and logic of configuration

# References
https://developer.hashicorp.com/terraform/language/style#style-guide
https://developer.hashicorp.com/terraform/language/block/check - API Reference section