---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-2-mapping-relationships
Draft: true
has-questions: true
---
# Questions
- When creating bidirectional entity associations for instance with `@OneToMany` in one entity and `@ManyToOne` in the other, one of the entities must have a `mappedBy` attribute, which matches the counterpart entity's name.
	- Does it matter which entity has the `mappedBy` attribute?

# See Also
https://docs.hibernate.org/jpa/2.1/api/javax/persistence/OneToMany.html
https://docs.hibernate.org/jpa/2.1/api/javax/persistence/ManyToOne.html
https://www.baeldung.com/jpa-joincolumn-vs-mappedby