---
tags:
  - reference-notes
  - database
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/db-indexing
Draft: false
has-questions: false
---

- Representation of a table
- Consumes additional memory
- Optimizes search
- Updates on each write
- May not be necessary with low reads vs writes

# Types
## B-Trees
- Default index
- Good for random inserts and deletes
- Self-balancing
- Sorted
- Good for range queries

## Hash Trees
- Exact match searches ONLY
- sorting and range queries are not supported
- Rarely used
## Geospatial
- Used primarily for location or proximity search
> [!note]
> B-trees are bad for indexing locations because it considers latitude and longitude as is as 2 separate entities. It can index both values but has to process data based on each data one at a time.
## Types of Geospatial Indexes
### Geohash
- Hashes 2d location data(latitude, longitude) into a hashed 1D string
- Example: `fa3Cv` -> `fa3Cva` and `fa3Cvb` are within `fa3Cv`
- Can be used with B-trees
- Simplest implementation
- Good for point locations
### QuadTrees
- Nodes that rigidly have 4 children
- Complex implementation
- Each node is a location -> children more specific location
### R-Trees
- Similar to QuadTrees but flexible instead
- modern spatial index
- flexible 

## Inverted Indexes
- Data is indexed based on content
- Good for text searches
- Example:
```
document -> [row1, row2]
hehe -> [row3]
this -> [row1, row3]
```

# Patterns
1. Composite Indexes - order matters
2. Including non-index key columns in indexes along with index keys
# Questions
- When you should you use geohash vs quadtrees vs r-trees

# References
https://www.hellointerview.com/learn/system-design/deep-dives/db-indexing