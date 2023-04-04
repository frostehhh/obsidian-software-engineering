---
aliases: [EC2 Basics]
---

![[Pasted image 20230319053642.png]]
EC2 instances can be configured to have a specific operating system - Windows, Linux, MacOS, etc.
![[Pasted image 20230319130451.png]]
Terminated - Completely deletes the instance

![[Pasted image 20230319130936.png]]
# Connecting to EC2
If connecting to a
- Windows - remote desktop protocol(RDP) to port 3389
- Linux - SSH protocol which runs on port 22. Login via SSH key-pair
![[Pasted image 20230319131451.png]]
## Logging in
- Linux - Use private and public key to authenticate and connect to the instance
- Windows - Private key is used to access local admin password of the instance, and then connect to the instance using the RDP using the local admin user and that password
# References
[Amazon Elastic Compute Cloud Documentation](https://docs.aws.amazon.com/ec2/index.html?nc2=h_ql_doc_ec2)