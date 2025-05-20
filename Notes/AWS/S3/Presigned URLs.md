---
tags:
  - notes
  - aws/s3
  - security/authentication
"related-reference-note:":
  - "[[Reference Notes/Adrian Cantrill/Amazon Web Services/Services/Simple Storage Service/Presigned URLs/Presigned URLs|Presigned URLs]]"
Draft: false
has-questions: false
---

- A pre-authenticated URL
- Actionable operations with the URL depend on the IAM permissions of who request the URL
- Use case - Providing a user with no access to a private S3 bucket a URL to a specific bucket and key so that they can upload/download
- Create a presigned URL by specifying object -> requires [[Bucket]] and [[Key]] and either GET or PUT operation

![[Pasted image 20230410043119.png]]

# References
[AWS S3 Documentation - Using presigned URLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html)
https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/Package/-aws-sdk-s3-request-presigner/
