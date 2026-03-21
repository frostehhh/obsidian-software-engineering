---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-2-mapping-relationships
Draft: true
has-questions: true
---

# Relationships
- one to one
- one to many
- many to one
- many to many
## One to one
- `@OneToOne` annotation
## Many to one and One to many
- `@ManyToOne` and `@OneToMany` annotation
- `@OneToMany(mappedBy = ...)` is used to make a relationship bidirectional. This value must reference the owner of the relationship
- `@ManyToOne(optional = false)` can be configured to make so that an association is required
	```java
	class Campaign {
		@OneToMany(mappedBy = "campaign")
		private List<Task> tasks;
		
		// ...
	}
	
	class Task {
		@ManyToOne
		@JoinColumn(name = "campaign_id")
		private Campaign campaign;
		// ...
	}
	```
> [!note]
> `@JoinColumn` is an optional annotation since there is a fallback mechanism for the foreign key name configuration

## Many to Many
- `@ManyToMany` annotation
### With JoinTable


### With a separate entity
- In a separate table that links two entities, add relationship mapping to the 2 relationships via `@ManyToOne`
```java
class WorkerSkill {
	@ManyToOne
	@JoinColumn(name = "worker_id")
	private List<Worker> workers;
	
	@ManyToOne()
	@JoinColumn(name = "skill_id")
	private List<Skill> skills;
}
```
# Questions
- When creating bidirectional entity associations for instance with `@OneToMany` in one entity and `@ManyToOne` in the other, one of the entities must have a `mappedBy` attribute, which matches the counterpart entity's name.
	- Does it matter which entity has the `mappedBy` attribute?

# See Also
https://docs.hibernate.org/jpa/2.1/api/javax/persistence/OneToMany.html
https://docs.hibernate.org/jpa/2.1/api/javax/persistence/ManyToOne.html
https://www.baeldung.com/jpa-joincolumn-vs-mappedby