---
tags:
  - system-design
source_url: https://highscalability.com/lessons-learned-from-scaling-uber-to-2000-engineers-1000-ser/
Source: HighScalability
author: HighScalability
---

# Uber
- Microservice's benefits are primarily regarding ownership like which team owns this microservice.
- Costs of microservices is a distributed system
	- How to know which service causes an issue
	- When you need to interact with a team about their microservice, it's possible to just build a new microservice and avoid the talk.
	- Each team can use their own tech stack
- Many tradeoffs due to the number of engineers, services and git repositories