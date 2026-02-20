---
tags:
  - reference-notes
  - java/junit
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-4-testing-our-functionality
Draft: false
---

# Outline
- structure of a unit test - given when then
- creating test cases
	- happy path
	- corner cases
	- state changes
- Unit tests vs integration tests
- IoC
- Mocking

# Structure of a Unit Test
Each unit test can be formatted via the structure "given-when-then".
Given - data needed
When - execution of action given a data
Then - assertion to verify output from actions

See also [[Unit Testing#Anatomy of a Unit Test[ 1]]]
# Unit Tests vs Integration Tests
Unit tests involve testing only of individual components
Integration tests involve testing of multiple components.
> [!note]
> There is a subtle difference in definition here compared to [[Integration Testing]] and [[Unit Testing]]

# Creating Test Cases
1. **Creating the happy path.** This involves creating the main workflow and what happens when a flow runs succesfully
2. **Creating the corner cases.** This involves other cases especially cases where there may be failures or unexpected outputs that may occur
3. **Tests for state changes.** If possible, test for state changes. For example, on save of a repository, check if an ID is internally generated for the saved item

# Inversion of Control
A design pattern where external sources are responsible for initializing dependencies. This simplifies usage of dependencies by other classes that require them

# Mocking
Mocking of data to provide a more detailed and complex data setup 