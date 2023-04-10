# Manually create a presigned URL via AWS Cloudshell
```
aws s3 presign [S3 URI] --expires-in 180
```

# Create via AWS console UI
Access object > See Actions > Click generate presigned URL

# References
[AWS S3 Documentation - Using presigned URLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html)