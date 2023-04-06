![[Pasted image 20230327004341.png]]
- An identity used for anything requiring long-term AWS access e.g. humans, applications, or service accounts
- 
![[Pasted image 20230327004657.png]]
In this example, a principal makes requests with IAM to interact with Amazon resources

**Principal** - any entity that interacts with IAM
**Authenticated Identity** - after authentication, a principal is identified as this

# Important Points
![[Pasted image 20230327010229.png]]
- 5000 IAM users per account
- IAM User can be a member of 10 groups
- This has systems design impacts...
- Internet scale applications
- Large orgs & org merges
- IAM Roles & Identity Federation fix this(more later)