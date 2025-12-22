---
tags:
  - reference-notes
  - system-design
  - guide
Draft: false
---

# Types of System Design interview[^1]
- Product Design - create system given particular usecase
- Infrastructure design - similar to product design except we are provided an existing infrastructure
- OOP Design - Low level design, classes
- Frontend Design

# Approach[^1]
1. Problem Identification
2. High-level Architecture
3. Technical Details
4. Proper communication and collaboration
# Delivery Framework[^2]
## System Requirements
1. Functional requirements
	user-functionality.
	For example, "user's can post tweets"
2. Non-functional requirements (AESLDFSC)
	 System capabilities. The search latency should be "<500ms"
	 - Availability vs Consistency([[CAP Theorem]])
	 - Environment Constraints
	 - Scalability
		 - peak times
		 - reads vs writes
	 - Latency
	 - Durability
	 - Fault tolerance
	 - Security
	 - Compliance
## Core Entities
Entities central to the system design. For example, when designing Twitter, we need `User`, `Tweet` and `Follow` entities
## API or System Interface
- RESTful API - can default to this
- GraphQL API
## High-level Architecture
Start building the initial high-level architecture and include the needed components: API Gateway, servers, Databases, etc.
## Deep Dives
Iterate on the high-level architecture based on what parts can be improved based on the given requirements
# Extra notes
- DAU - Daily active users
# Questions
- When should we use GraphQL API
- What is an API Gateway for?

[^1]: https://www.hellointerview.com/learn/system-design/in-a-hurry/how-to-prepare
[^2]: https://www.hellointerview.com/learn/system-design/in-a-hurry/delivery


