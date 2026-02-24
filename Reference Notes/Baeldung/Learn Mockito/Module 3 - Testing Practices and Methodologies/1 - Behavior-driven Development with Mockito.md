---
tags:
  - reference-notes
  - java/mockito
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-mockito/lessons/lesson-1-behavior-driven-development-bdd-with-mockito-2
Draft: false
---

# What is BDD
Behavior-driven development is a method of development where the perspective of the user is prioritized when creating tests such that tests are written in a way that is easily readable to non-tech people.

`Given-when-then` is a commonly used method of describing tests in this regard

# How to perform TDD?
To do TDD, we can use the `red-green-refactor` method. Red, create tests and let them fail. Green, create enough code just to have the tests succeed. Lastly, refactor to clean up the code

# BDDMockito
BDDMockito uses syntax very similar to vanilla Mockito. To conform with BDD, the syntax is changed slightly to match the `given-when-then` practice.

Since the difference between BDDMockito and Mockito is merely syntax-wise, the choice between the two is primarily a matter of preference among teams

# See Also
https://en.wikipedia.org/wiki/GRASP_(object-oriented_design)#Information_expert