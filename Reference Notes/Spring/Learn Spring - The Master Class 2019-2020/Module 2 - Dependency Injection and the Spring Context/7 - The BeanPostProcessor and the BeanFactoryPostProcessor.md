---
tags:
  - reference-notes
  - spring
source_url:
---

# Interfaces
## BeanPostProcessor
- to be implemented by class
- postProcessBeforeInitialization
- postProcessAfterInitialization
- When there are multiple classes that implement `BeanPostProcessor`, implement the `Ordered` interface
## BeanFactoryPostProcessor
- postProcessBeanFactory
## FactoryBean
- interface to configure bean creation
- ex. can change default scope to prototype instead of singleton

