---
tags:
  - guide
  - reference-notes
  - system-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/system-design/problem-breakdowns/dropbox
has-questions: true
---

# Requirements
## Functional

## Non-functional

# Core Entities
- User
- File
# API
```
GET /files/{id} -> File, FileMetadata
POST /files
{
   FileMetadata
}
```

# High-level Architecture
# Deep Dives


# Questions
- pre-signed url? S3?
- file upload limits to api gateway, loadbalancer etc.
- uploading large files in chunks - depth
	- how to decide chunk size?
	- chunk state info?
	- Update DB chunk state while uploading?
- downloading large files resumable?