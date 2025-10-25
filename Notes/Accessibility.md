---
tags:
  - notes
  - accessibility
  - html
Draft: true
---

# What is Accessibility?
Accessibility is consideration for person with disabilities including but not limited to vision, hearing to make software more accessible to use especially via screen readers.


# Tools for Evaluating Accessibility Implementation

> [!note] Explore available accessibility tools
> There may be good accessibility extensions on VSCode and other free tools


# Fundamentals
1. No ARIA is better than bad ARIA
2. Always allow keyboard navigation
3. Use proper ARIA attributes for interactive elements such as form elements
4. Do not use unnecessary ARIA attributes
5. ?

# How Tos

## Content
- Proper usage of HTML semantic elements[^1] rather than generic `div` elements
- use heading elements(h1, h2, h3) based on content. Separate styling from the usage of those elements
## JavaScript
- Dynamic functionalities, HTML and CSS injected by JS tends to lack accessibility considerations
	- Ex. onFocus - no accessibility support, CSS `:focus` has accessibility support
## Document
- Title element must be cohesive
- Text must be structured from sections to subsections
	- ex. Season 3 | Epidode 1 | The episodening
## Links
- There must be a description for the link via alt text
- Must be navigatable

## Images
### Presentational
- role="presentation"
- empty or null alt text
- aria-hidden
### Functional
- alt text
### Complex
# References
[web.dev - Accessibility](https://web.dev/learn/accessibility/welcome)

[^1]: https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements
