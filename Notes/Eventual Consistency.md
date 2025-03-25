---
tags:
  - database
  - notes
Draft: true
Parent:: 
- "[[Notes/ACID/Consistency|Consistency]]"
---

After an update, there is a delay between the initial update and the state when all instances of the data are synchronized

# When to use
- Data is not important to synchronize with other data
- Examples
	- Notifications
	- Chat messages
	- Tweets

# When not to use
- Financial systems
- Banks

# Examples of where this can occur
- Relational databases with multiple replicas
- NoSQL databases