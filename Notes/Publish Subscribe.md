---
tags:
  - notes
  - backend
  - backend
  - networking/communication
Draft: false
aliases:
  - Pub Sub
---

Publish subscribe, also informally called pub sub, is a one-to-many communication model where changes are published and subscribers are alerted of this change.
Usually, messages are published to topics. Subscribers get these messages.
# Pros
- Scalable
- Non-blocking as opposed to if you would achieve a similar function as with [[Request Response Model]]
- Good for microservices
- Loose coupling
- Works while clients not working
# Cons
- Message deliverability issues
	- message can unexpectedly be processed twice
- Complexity
	- Another layer of a broker of messages
- Network saturation