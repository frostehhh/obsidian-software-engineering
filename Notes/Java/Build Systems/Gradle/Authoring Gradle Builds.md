---
tags:
  - notes
  - programming-languages/java
  - build-tools/gradle
Draft: true
Parent:: "[[Gradle]]"
---

# Lifecycle
1. initialization
2. configuration
	 Evaluate settings and build files. Then, create task graph
3. execution
   Task graph execution

# Writing Build Scripts

- Simple example

Example
```kotlin
plugins {
    id("java")
}

repositories {
    mavenCentral()
}

dependencies {
    testImplementation("junit:junit:4.13")
    implementation(project(":shared"))
}
```


# Declaring Dependencies
# Creating and Registering Tasks
- Can create new tasks that can be executed via `./gradlew <task-name>` via `task.register<>{...}`