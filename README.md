# Question 1 — AWS Networking & Subnetting (VPC Setup)

1. Brief Explanation
I created a VPC with CIDR `10.0.0.0/16` and divided it into 4 subnets:  
- Two public subnets (`10.0.1.0/24`, `10.0.2.0/24`) placed in different AZs  
- Two private subnets (`10.0.3.0/24`, `10.0.4.0/24`) also across AZs  
An Internet Gateway was attached to allow internet access for public subnets.  
A NAT Gateway (in public subnet A) allows private subnets to access the internet for updates while remaining unreachable from outside.

2. CIDR Ranges Used
- VPC: 10.0.0.0/16  
- Public Subnet A: 10.0.1.0/24  
- Public Subnet B: 10.0.2.0/24  
- Private Subnet A: 10.0.3.0/24  
- Private Subnet B: 10.0.4.0/24  

Why these ranges? 
They are simple, non-overlapping `/24` networks that make routing and subnetting easy. `/16` for VPC provides enough space for scaling.

3. Screenshots
- VPC: `screenshots/vpc.png`  
- Subnets: `screenshots/subnets.png`  
- Route Tables: `screenshots/route-tables.png`  
- NAT Gateway + IGW: `screenshots/nat-igw.png`  

4. Terraform Code
All Terraform code for this question is in `main.tf`.

5. Cleanup
All AWS resources were deleted after completing the assessment.
