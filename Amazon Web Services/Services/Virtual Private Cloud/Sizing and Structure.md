
# Considerations
![[Pasted image 20230411003358.png]]

# Example
## Global Architecture
![[Pasted image 20230411010843.png]]
## IP Ranges to Avoid
![[Pasted image 20230411011120.png]]

# More Considerations
![[Pasted image 20230411012521.png]]

# VPC Sizing
![[Pasted image 20230411013437.png]]
# VPC Structure
![[Pasted image 20230411014005.png]]
> [!note] 
>  When deciding how many availability zones we'll use when configuring a VPC, best to default to 3 since all regions in AWS have a minimum of 3 availability zones. In addition to that, we should also consider space for 1 spare availability zone

# Proposal
![[Pasted image 20230411014958.png]]
# Related Course Lesson
https://learn.cantrill.io/courses/1820301/lectures/41301346

# Course Links
[https://aws.amazon.com/answers/networking/aws-single-vpc-design/](https://aws.amazon.com/answers/networking/aws-single-vpc-design/)
[https://cloud.google.com/vpc/docs/vpc](https://cloud.google.com/vpc/docs/vpc)
[https://github.com/acantril/aws-sa-associate-saac02/tree/master/07-VPC-Basics/01_vpc_sizing_and_structure](https://github.com/acantril/aws-sa-associate-saac02/tree/master/07-VPC-Basics/01_vpc_sizing_and_structure)
