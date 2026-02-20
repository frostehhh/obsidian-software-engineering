---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-1-execution-order
Draft: false
---

Test execution order is not guaranteed ordered by default
# Annotations
- `TestClassOrder`
- `TestMethodOrder`
Both of these annotations are expected as the class level

# Ordering For Each Annotation
- display name
- class name
- order annotation
- random

Ordering config is available via the `MethodOrderer` helper

# Examples
```java
@TestMethodOrder(MethodOrderer.OrderAnnotation.class)
class MethodOrderAnnotationUnitTest {
    private static final AtomicInteger counter = new AtomicInteger(1);

    @Test
    @Order(3)
    void testOne() {
        System.out.println("Running testOne, order 3");
        Assertions.assertEquals(3, counter.getAndIncrement());
    }

    @Test
    @Order(1)
    void testTwo() {
        System.out.println("Running testTwo, order 1");
        Assertions.assertEquals(1, counter.getAndIncrement());
    }

    @Test
    @Order(2)
    void testThree() {
        System.out.println("Running testThree, order 2");
        Assertions.assertEquals(2, counter.getAndIncrement());
    }
}
```
