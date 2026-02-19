---
tags:
  - notes
  - java
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
## Examples
```kotlin
dependencies {
    implementation("com.google.guava:guava:30.0-jre")
    runtimeOnly("org.apache.commons:commons-lang3:3.14.0")
}
```
## Types
1. Module
2. Project
3. File

| Type    | Description                            | Reference                                                     |
| ------- | -------------------------------------- | ------------------------------------------------------------- |
| Module  | Most common dependency type            | `implementation`                                              |
| Project | Declare dependency on other subproject | `implementation(project(":my-project-name")`                  |
| File    | Self-hosted dependencies               | `runtimeOnly(files(""))` or `runtimeOnly(filetree(...){...})` |
|         |                                        |                                                               |
|         |                                        |                                                               |
### Dependency Configurations
| Configuration Name   | Description                                                                                | Used to:             |
| -------------------- | ------------------------------------------------------------------------------------------ | -------------------- |
| `api`                | Dependencies required for both compilation and runtime, and included in the published API. | Declare Dependencies |
| `implementation`     | Dependencies required for both compilation and runtime.                                    | Declare Dependencies |
| `compileOnly`        | Dependencies needed only for compilation, not included in runtime or publication.          | Declare Dependencies |
| `compileOnlyApi`     | Dependencies needed only for compilation, but included in the published API.               | Declare Dependencies |
| `runtimeOnly`        | Dependencies needed only at runtime, not included in the compile classpath.                | Declare Dependencies |
| `testImplementation` | Dependencies required for compiling and running tests.                                     | Declare Dependencies |
| `testCompileOnly`    | Dependencies needed only for test compilation.                                             | Declare Dependencies |
| `testRuntimeOnly`    | Dependencies needed only for running tests.                                                | Declare Dependencies |

### [](https://docs.gradle.org/current/userguide/dependency_configurations.html#sub:dependency-declaration-configurations)[Dependency declaration Configurations](https://docs.gradle.org/current/userguide/dependency_configurations.html#sub:dependency-declaration-configurations)
# Creating and Registering Tasks
- Can create new tasks that can be executed via `./gradlew <task-name>` via `task.register<>{...}`

# References
https://docs.gradle.org/current/userguide/gradle_directories_intermediate.html