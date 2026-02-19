---
tags:
  - notes
  - java
  - build-tools/gradle
Draft: true
Parent:: "[[Java Build System]]"
---

# Core Concepts[^1]
- build
- task
- wrapper
- settings
- plugins
- dependency

## Wrapper[^2]
Files
- gradle-wrapper.jar
- gradle-wrapper.properties
- gradlew
- gradlew.bat

> [!warning]
> These files must not be altered

## Commands
Some commands but not all
- build
- test
These are also called **tasks**

## Settings[^3]
- rootProject.name - required
- `include` include other subprojects
	```
	settings.gradle(.kts)
	/subproject-a
	  build.gradle(.kts)
	```
## Tasks[^4]
- Basic unit of function in Gradle
	- `gradle tasks` - view list of tasks

## Caching[^5]
- incremental builds
- build caching
## Plugins[^6]
- adds configuration
- Add DSL configurations
- Specified via `plugin` block

# References


[^1]: https://docs.gradle.org/current/userguide/gradle_basics.html

[^2]: https://docs.gradle.org/current/userguide/gradle_wrapper_basics.html

[^3]: https://docs.gradle.org/current/userguide/settings_file_basics.html

[^4]: https://docs.gradle.org/current/userguide/task_basics.html

[^5]: https://docs.gradle.org/current/userguide/gradle_optimizations.html

[^6]: https://docs.gradle.org/current/userguide/plugin_basics.html
