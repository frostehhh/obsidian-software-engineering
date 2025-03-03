https://learn.cantrill.io/courses/1820301/lectures/42262547

# Steps
1. Create CloudFormation stack via stack template URL
2. Launch EC2 instance A4L-INTERNAL-TEST, which is on sn-web-A
3. Create 3 NAT gateways for each availability zone A, B, C
4. Associate NAT gateway with availability zones A, B, C
5. Configure route table for each availability zone so that private instances can communicate via the NAT gateway
6. In each route table, add a default route 0.0.0.0/0 that'll target the created NAT gateway for the current availability zone
7. Route tables should have explicit association to subnets. Do this. app, db, reserved subnets