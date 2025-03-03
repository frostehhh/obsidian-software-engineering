![[Pasted image 20230402050839.png]]
- IAM role linked to a specific AWS service
- Predefined by a service
- Providing permissions that a service needs to interact with other AWS services on your behalf
- Service might create/delete that role
- or allow you to during the setup or within IAM
- You can't delete the role until it's no longer required

![[Pasted image 20230402051244.png]]

# PassRole
![[Pasted image 20230402051824.png]]
Pass an existing role into an existing service

# References
[https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html)