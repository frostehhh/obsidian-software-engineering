---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-2-mapping-relationships
Draft: false
has-questions: false
---

# Relationships
- one to one
- one to many
- many to one
- many to many
## Embeddable
- `@Embeddable` is used to mark a class as embeddable
	- Makes it conveniently reusable
- Used to map a class and its properties to specific columns in the underlying database table
- `@Embedded`, `@AttributeOverrides` and `@AttributeOverride` annotations is used in an entity class member 
```java
@Embedded
@AttributeOverrides({
  @AttributeOverride(name = "street", column = @Column(name = "address_street")),
  @AttributeOverride(name = "city", column = @Column(name = "address_city")),
  @AttributeOverride(name = "zipCode", column = @Column(name = "address_zip_code"))
})
private Address address;
```
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
- `@JoinTable` annotation
	```java
	// in Task entity
	@ManyToMany
	@JoinTable(
	  name = "Task_Label",
	  joinColumns = @JoinColumn(name = "task_id"),
	  inverseJoinColumns = @JoinColumn(name = "label_id")
	)
	private Set<Label> labels = new HashSet<>();
	
	// in Label entity
	@ManyToMany(mappedBy = "labels")
	private Set<Task> tasks = new HashSet<>();
	```

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

@Entity
class Worker {
    // ... existing fields

    @OneToMany(mappedBy = "worker")
    private Set<WorkerSkill> workerSkills = new HashSet<>();

    // setters and getters
}

@Entity
class Skill {
    // ... existing fields

    @OneToMany(mappedBy = "skill")
    private Set<WorkerSkill> workerSkills = new HashSet<>();

    // setters and getters
}
```
# Questions


# See Also
https://docs.hibernate.org/jpa/2.1/api/javax/persistence/OneToMany.html
https://docs.hibernate.org/jpa/2.1/api/javax/persistence/ManyToOne.html
https://www.baeldung.com/jpa-joincolumn-vs-mappedby