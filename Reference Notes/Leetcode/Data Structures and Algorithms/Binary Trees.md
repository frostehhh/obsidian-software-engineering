---
tags:
  - reference-notes
  - pattern
  - algorithms
source_url: https://leetcode.com/explore/interview/card/leetcodes-interview-crash-course-data-structures-and-algorithms/707/traversals-trees-graphs/4686/
Draft: true
---

- Tree data structures that use the concept of nodes similar to [[Linked Lists]]
- Each node has a max of 2 children, commonly referred to as `left` and `right`
- Traversal can be either via depth-first search or breadth-first search

# Important Terminologies
- Root - parent node
- Leaf - node with no children
- Subtree - non-root node with all of its descendants
- depth - distance from the root node. Root node has a depth of 0
# Depth-first Search
- Preorder
- Inorder
- Postorder

# Breadth-first Search
- Searches from top to bottom

## Sample Code
```javascript
const bfs = (node) => {
	const queue = [node]
	
	while(queue.length >= 1) {
		const nextQueue = []
		const currLength = queue.length;
		
		for (let i = 0; i < currLength; i++) {
			//... processing
			const currNode = queue[i];
			if (currNode.left) {
				nextQueue.push(currNode.left)
			}
			if (currNode.right) {
				nextQueue.push(currNode.right)
			}
		}
		
		queue = nextQueue
	}
	
	return;
}
```


# Binary search trees
