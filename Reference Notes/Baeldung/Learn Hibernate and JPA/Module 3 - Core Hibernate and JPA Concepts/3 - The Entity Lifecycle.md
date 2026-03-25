---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-3-the-entity-lifecycle
Draft: false
---

# Lifecycle
1. Transient
2. Managed
3. Detached
4. Removed

## Transient
- new object
- not yet handled by the persistence context
## Managed
- entity is persisted and is expected to exist in the persistence context
- updates are tracked
## Detached
- removed from persistence context
- can be reincluded via `merge()`
## Removed
- entity marked as to remove after transaction is commited
- can be persisted and moved to a managed state after invoking `persist()`