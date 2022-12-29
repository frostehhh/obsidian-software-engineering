---
aliases: [AWSCLI]
tags: [cli]
---

# Quickstart
`aws configure` in command line to start configuration. Use the `--profile` flag to configure a named profile

If you have a named profile, you can run `aws` commands with a chosen named profile by adding a `--profile` flag to that command. For example

```
aws configure --profile sample-profile
<Configuration here>

aws s3 ls --profile sample-profile
```
