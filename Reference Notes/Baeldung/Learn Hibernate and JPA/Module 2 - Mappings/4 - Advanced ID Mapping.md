---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-4-advanced-id-mapping
Draft: true
has-questions: true
---

# ID Generation
- AUTO - auto selects ID generation method
- Identity
	- auto increments integer value
	- ID is known only after INSERT action is performed
- UUID
- Sequence
	- Exists outside of the database
	- Similar to Identity but provides more flexibility
- Table
	- alternative to Sequence
	- Used in case Sequence is not supported by the underlying database solution

# Composite Keys
- @EmbeddedId or @IdClass for mapping composite primary keys
# Natural and Surrogate Keys
- Surrogate key
	- key value with no business relevance
	- only uniquely identifies entities
	- Easier to optimize lookups
	- example
		- UUID
- Natural key
	- key value with business relevance
	- Can use `@NaturalId` annotation to mark a property as natural key
		- This also optimizes lookups for this field
	- example
		- user email
		- organization name

# Questions
- What is the difference between Identity and Sequence
- EmbeddedId vs IdClass?
	- look for relevant docs

# See Also
https://vladmihalcea.com/hibernate-identity-sequence-and-table-sequence-generator/
https://www.baeldung.com/hibernate-identifiers