---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-3-setting-up-hibernate-and-jpa
Draft: true
has-questions: true
---

# Setting up
- Dependencies via pom.xml since we're using Maven
	- hibernate.core
	- h2 database as the option for the persistence storage
- persistence.xml in the [[META-INF]]
	- persistence configuration
	- includes persistence storage option(h2 in our case)
- Hooking up the `Worker` class to be marked as an persistence entity
- Using the `Persistence` API to create a entity manager factory
	```java
	Persistence.createEntityManagerFactory("LHJ");
	```
# See also
https://openjpa.apache.org/builds/1.2.3/apache-openjpa/docs/jpa_overview_persistence.html#:~:text=xml%20.-,1.,xml&text=The%20root%20element%20of%20a,of%20the%20PersistenceProvider%20bootstrapping%20interface.