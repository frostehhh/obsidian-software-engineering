---
tags:
  - reference-notes
  - java/collections
  - concurrency
  - synchronization
  - computer-science/locks
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-5-concurrent-collections
Draft: false
---

- `Collections` class `synchronized*` wrappers
	- Examples: `synchronizedSet`, `synchronizedMap`
	- All methods are run serially by a single lock coupled to the object
	- Synchronization exists only for single method usages. Compound actions are still prone to desynchronization of data

# Key Classes Discussed
## ConcurrentHashMap
- Allows concurrent reads and writes without synchronizing them
- Allows more throughput compared to `synchronized*` counterpart

## CopyOnWriteArrayList
- A thread accessing this object creates a snapshot of the object prior to processing it
- Hence, if another thread updates the object, the preceding thread will not be able to see any concurrent updates.
- Good for frequent reads and seldom writes due to a new copy of the array being created on write
	- May be slow

```java
@Test  
void givenObserverList_whenIteratingAndAdding_thenIterationUsesSnapshot() throws InterruptedException {  
    CopyOnWriteArrayList<String> observers = new CopyOnWriteArrayList<>();  
    observers.add("Observer A");  
    observers.add("Observer B");  
  
    List<String> seenDuringIteration = new ArrayList<>();  
  
    Thread reader = new Thread(() -> {  
        for (String obs : observers) {  
            seenDuringIteration.add(obs);  
            try {  
                Thread.sleep(50); // simulate slow iteration  
            } catch (InterruptedException ignored) {}  
        }  
    });  
  
    Thread writer = new Thread(() -> {  
        observers.add("New Observer A");  
        observers.add("New Observer B");  
    });  
  
    reader.start();  
    writer.start();  
    reader.join();  
    writer.join();  
  
    // The iterator only saw the original snapshot even if we add in the list new items  
    assertEquals(List.of("Observer A", "Observer B"), seenDuringIteration);  
  
    // The new observers were added, but only visible after iteration  
    assertTrue(observers.contains("New Observer A"));  
    assertTrue(observers.contains("New Observer B"));  
}
```
