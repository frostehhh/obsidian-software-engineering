---
tags:
  - reference-notes
  - database/nosql
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/dynamodb
Draft: false
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

# Capabilities
## Scaling
- automatic sharding and load balancing
- Support global tables and cross-region replication
## Fault Tolerance and Availability
- Automatically replicated to multiple [[AWS Global Infrastructure#Availability Zone]]
## Security
- encrypted at rest
- optional encryption on transit
# Pricing Model
- 1 eventually consistent read -> 0.5 read cost units(RCU)
- 1 RCU is up to 4kb
	- Cost is rounded up to the nearest whole KB
- 1 Write cost unit(WCU) is up to 1kb
	- Cost is also rounded up to the nearest whole KB
- Can consider these to ensure no unrealistic costs will occur

## Other Features
### DAX
Caching capability
### Streams
- Change Data Capture(CDC) - log of data changes
- Purpose
	- Data analytics
	- ElasticSearch syncing
	- notifications based on changes

# When not to use
- unrealistic costs
- vendor lock-in to AWS
- Too strict data model due to GSI and LSI
- Inability for complex query patterns
