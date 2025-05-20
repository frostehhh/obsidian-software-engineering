---
tags:
  - guide
  - reference-notes
  - system-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/system-design/problem-breakdowns/dropbox
has-questions: true
---

# Timestamps
https://www.youtube.com/watch?v=_UZ1ngy-kOI&t=0
41:30 low latency
45:40 high data integrity
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
## Handling large file uploads
- Upload and download directly to S3
	- Can manually implement chunking and update file metadata along the way
	- Alternatively, S3 multipart upload
- Use API to get presigned-url and perform uploads and downloads through that
- Use API to update file metadata
## Syncing local changes and remote changes
- short polling simplest solution
- Long polling - expects a response, but not necessary for this case
- Websockets - persistent connection and also expects a response in a way. No as well.
- Event bus - actual implementation at Dropbox(overkill for simple case, but still an option)
- 
## low latency downloads and uploads
- Compression
- Update FileMetadata to include compression algorithm used

# Questions
- pre-signed url? S3?
	- how does it work?
	- how to use
- file upload limits to api gateway, loadbalancer etc.
- uploading large files in chunks - depth
	- how to decide chunk size?
	- chunk state info?
	- Update DB chunk state while uploading?
- downloading large files resumable?
- CDN - do uploads go through a CDN?
- websocket max connections?
- delta sync?only fetch changed chunks
- how does the API change based on deep dive changes?
	- chunking?
- dropbox blog on design?
- reconciliation?
- 