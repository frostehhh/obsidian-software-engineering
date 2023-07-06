- Use a `-ENVIRONMENT_NAME` naming convention especially when multiple environments are needed
# Add Multi-Factor Authentication(MFA)
	- Access under Security Credentials
	- ![[Pasted image 20230701150016.png]]
# Set billing notifications
	 ![[Pasted image 20230701150051.png]]
	 ![[Pasted image 20230701150230.png]]
# Set budget
 ![[Pasted image 20230701150259.png]]
 Create preferred budget. Can do zero-spend budget by default for personal use.
# Activate cost explorer
 Enable `IAM User & Role Access to Billing`
 Access via account name dropdown, then `Account`. Lastly, go to `IAM User and Role Access to Billing Information`
# Setup Account Alias in [[Identity and Access Management Basics|IAM]]
# Create normal admin user
Create IAM user. You can give a username of `iamadmin` as a convention.
Attach `AdministratorAccess` policy

# Enable IAM user/role access to billing information
![[Pasted image 20230707023334.png]]