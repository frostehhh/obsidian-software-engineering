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
- persistence.xml
	- persistence configuration
	- includes persistence storage option(h2 in our case)
- Hooking up the `Worker` class to be marked as an persistence entity

# Questions
- What is the META-INF directory for? Is it particularly a JPA spec?
- Where is the documentation for the META-INF directory and the persistence.xml file?