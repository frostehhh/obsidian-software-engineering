---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-6-inheritance-mapping-advanced
Draft: false
---

# Other Inheritance Mapping Methods
- Table by class
- Joined Table
- Mapped superclass

# Table by Class
- one table per class
- when querying with the superclass, will need to perform `UNION` operations
	- May be slow with polymorphic queries -> querying superclass
	- no performance issues when querying only subclasses
- To synchronize the ID generation, a separate id generator table + entity can be created
- There may be field redundancy since the subclasses can inherit common fields from the superclass. This results to the multiple tables having redundant fields
```java
@Entity
@Inheritance(strategy = InheritanceType.TABLE_PER_CLASS)
public abstract class Worker {
    @Id
    @GeneratedValue(strategy = GenerationType.TABLE, generator = "worker_id_generator")
    @TableGenerator(
        name = "worker_id_generator",
        table = "id_generator",
        pkColumnName = "generator_name",
        pkColumnValue = "worker_id",
        valueColumnName = "next_generator_value"
    )
    @Column(name = "id")
    private Long id;

    // ...
}
```

# Joined Table
- Tables involved
	- Main table - represents superclass
		- has all common field values
	- Subclass tables
		- has fields that are unique to a subclass
- Avoids the issue with having redundant fields across different tables
	- solution is normalized
```java
@Entity
@Inheritance(strategy = InheritanceType.TABLE_PER_CLASS)
public abstract class Worker {
    @Id
    @GeneratedValue(strategy = GenerationType.TABLE, generator = "worker_id_generator")
    @TableGenerator(
        name = "worker_id_generator",
        table = "id_generator",
        pkColumnName = "generator_name",
        pkColumnValue = "worker_id",
        valueColumnName = "next_generator_value"
    )
    @Column(name = "id")
    private Long id;

    // ...
}
```

# Mapped Superclass
- The superclass is not an entity, but it is mapped onto the subclasses
	- As a result, does not support polymorphic queries because- does not support polymorphic queries 
- Similar to Table by class but without the ID sequence table
