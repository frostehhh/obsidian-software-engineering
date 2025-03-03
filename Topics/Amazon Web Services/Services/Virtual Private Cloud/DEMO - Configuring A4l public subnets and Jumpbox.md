# Course Demo Reference
https://learn.cantrill.io/courses/1820301/lectures/41301352

# Summary
In this [DEMO] Lesson we implement an Internet Gateway, Route Tables and Routes within the Animals4life VPC to support the WEB public subnets.

Once the WEB subnets are public, we create a bastion host with public IPv4 addressing and connect to it to test.

By the end of this [DEMO] you will have a fully working public capable VPC and bastion ingress point.

# Steps
1. Create [[Routing, Internet gateway & Bastion#Internet Gateway|Internet Gateway]] for the `a4l-vpc1`
2. Add Route table for the `sn-web-X` subnets.
3. In this route table, add a default route `0.0.0.0/0` and `::/0` for IPv4 and IPv6
4. Enable auto IPv4 Addressing for the mentioned subnets
5. Create Bastion via EC2 instance deployed onto `sn-web-A`.
6. Clear all VPC configuration for A4L