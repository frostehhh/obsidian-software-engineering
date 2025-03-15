![[Pasted image 20230327010945.png]]
- Containers for [[IAM Users]]
- Can't login to IAM Groups, and they have no credentials
- Can have policies attached to them regardless of inline or managed policies
- No limit to users in an IAM group
- Cannot have nested groups
- By default, 300 groups limit, but can be extended via support ticket

![[Pasted image 20230327011151.png]]
Groups are <mark style="background: #FF5582A6;">not a true identity</mark>. They can't be referenced as a principal in a policy