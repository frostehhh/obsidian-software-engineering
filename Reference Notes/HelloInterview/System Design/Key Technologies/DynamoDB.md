---
tags:
  - reference-notes
  - backend
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/kafka
Draft: true
has-questions: false
---

AWS NoSQL Database solution

# Data Model
- Table
- Item - rows
- Attribute - columns

## Primary key
- partition key + sort key
- sort key is optional
## Indexes
### Global secondary index
- Limit of 20
- eventually consistent
- No size limit
- In a different partition from the main table
### Local Secondary index
- limit of 5
- Strongly consistent always
- Limit of 10gb
- In same partition of main table
- Deleted along with the main table

