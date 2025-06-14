---
tags:
  - reference-notes
  - pattern
  - algorithms
---

# Two Pointers
- method of navigating a list or an array via a pointer at the start and a pointer at the end

# Sliding Windows
- Application of [[#Two Pointers]] where the pointers may move at the same direction 

# Prefix Sum
- Array of sums from 0 to i
- Can be also just an integer where the integer is the sum from 0 to i

# O(n) string building
- In programming languages with immutable string data types, adding `n` letters to a string may cost `O(n^2)` 
	- Adding one character to an immutable string will cost `O(stringLength)` due to needing to copy the entire string
- Better to build the string via a loop by adding a character in each iteration

# Subarrays/substrings, subsets and sub sequences?

# 

# References
https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/703/arraystrings/4500/
https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/703/arraystrings/4501/