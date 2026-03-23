---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-2-entity-relationships-and-operations
Draft: true
---

# Cascade Operations
- persist - if an entity contains child entities and the parent entity is persisted, the child entities are also persisted to their corresponding tables
- merge - if an entity updated its child entities, when the entity is saved, changes will be cascaded to the child entities
- detach
	- detach from context
	- will dive in  another chapter
- refresh
	- refresh to ensure updated data
	- unsaved changes are discarded
	- will dive in another chapter
- all
	- will include all cascade operations above

```java
@OneToMany(mappedBy = "campaign", cascade = {CascadeType.PERSIST, CascadeType.MERGE}) 
private Set<Task> tasks = new HashSet<>();
```
> [!note]
> Can specify multiple cascade operations


# orphanRemoval
- entity child instance is removed if it no longer has a reference to parent
```java
@OneToMany(mappedBy = "campaign", cascade = CascadeType.ALL, orphanRemoval = true)
private Set<Task> tasks = new HashSet<>();
```


# fetchType
- specifies when child entities are to be fetched
- will dive in another chapter

```java
@OneToMany(mappedBy = "campaign", orphanRemoval = true, fetch = FetchType.EAGER, cascade = CascadeType.ALL)
private Set<Task> tasks = new HashSet<>();
```