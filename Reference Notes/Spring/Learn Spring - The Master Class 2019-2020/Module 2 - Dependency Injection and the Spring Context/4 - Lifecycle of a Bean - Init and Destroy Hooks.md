---
tags:
  - reference-notes
  - spring
source_url: https://courses.baeldung.com/courses/487981/lectures/10286758
---

# Lifecycle
1. Initialization
2. standard usage
3. Destroy

# Annotation Lifecycle Hooks
- preConstruct
- preDestroy

@Bean(initMethod = "myInitialize")
@Bean(destroyMethod = "myDestroy")