---
tags:
  - reference-notes
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/elasticsearch
Draft: true
---

- Tool for optimizing searches
- Supports most if not all scenarios necessary for searching

# Concepts
1. Document - record
2. Index - value to search by
3. Mapping - schema of fields
4. Field - a field and its datatype

# Interacting with ElasticSearch via REST API

- Create index
- Create index mapping
- Get query
- Sort Query
- Create document
- Delete(?)
- Update document
	- PUT to replace whole document or
	- POST replace specified data
- Pagination
	- Stateful - internally, reads all pages from x to starting page and drops those pages, and then returns the next page to fulfill size
		- Starting page
		- Size
	- Stateless - finds search_after record and returns page based on size
		- search_after
		- size
		
> [!info]
> This is discussed in [[SQL Pagination with Offset is Very slow]]
