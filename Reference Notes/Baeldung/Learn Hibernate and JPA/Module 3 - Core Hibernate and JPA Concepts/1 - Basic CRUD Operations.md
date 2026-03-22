---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-1-basic-crud-operations
Draft: true
---

- Involves creating an `EntityManager` instance for interacting with entities
	- Can be created via factory pattern with `EntityManagerFactory`
- can use transactions
	- `entityManager.getTransaction()`
		- `begin()`
		- `commit()`
- operations
	- create - persist()
	- read - find()
	- update
		- find
		- update fields
		- commit()
	- remove