---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-3-dynamic-tests
Draft: false
---

- A way to create tests during runtime rather compile time
- `@TestFactory`
- Main method must return `Stream<DynamicTest>` or `Stream<DynamicNode>`
- `DynamicContainer` is used to logically group multiple `DynamicNode`
	- Note that `DynamicContainer` and `DynamicTest` both extend `DynamicNode`

```java
@TestFactory
Stream Stream<DynamicNode> givenSourceFiles_whenVerifyingAllNestedFiles_thenTheyAreNotTooLong() {
    return verifyAllNestedFolders(
      new File("src/main/java", "com/baeldung/lju"));
}

static Stream<DynamicNode> verifyAllNestedFolders(File root) {
    if (root.listFiles() == null) {
        return Stream.empty();
    }
    return Stream.of(root.listFiles())
      .map(file -> {
          if (file.getName().endsWith(".java")) {
              return verifyFileLength(file);
          } else {
              return DynamicContariner.dynamicContainer(
                  file.getName(),
                  verifyAllNestedFolders(file)
              );
          }
      });
}

static DynamicTest verifyFileLength(File javaFile) {
        return DynamicTest.dynamicTest(
            String.format("%s < %s lines", javaFile.getName(), MAX_FILE_LENGTH),
            () -> {
                long fileLength = Files.lines(javaFile.toPath()).count();
                assertTrue(fileLength < MAX_FILE_LENGTH);
            }
        );
    }
```

