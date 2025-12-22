---
tags:
  - reference-notes
  - backend
  - system-design/patterns
source_url: https://www.hellointerview.com/learn/system-design/patterns/long-running-tasks
Draft: false
---

For any long running tasks that take more than a few seconds to return a response, the typical solution is to make it asynchronous.

# Sample Flow
1. Client sends request
2. Server receives this and creates job in database with status pending
3. Server pushes the job to a job queue
4. A worker pops the next available job and blocks it. This job will be processed. The corresponding job record in the database will be updated to in_progress
5. When the job is done, the worker will update the job in the database

# Common Deep Dives
## How do you handle abuse?
Users can execute a batch action multiple times. This can be mitigated by having an idempotent key. For instance, an indempotent key can be a combination of these: userId, actionId, timestamp rounded off to a time interval depending on how long each batch action must be spaced

## How do you handle repeated failures?
Specify retry limit and jobs that fail past the retry limit are moved to a [[SQS Dead-Letter Queues]]