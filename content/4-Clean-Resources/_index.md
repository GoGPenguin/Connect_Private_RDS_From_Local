+++
title = "Clean Up Resources"
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

- [Delete RDS](#delete-rds)
- [Delete EC2](#delete-ec2)
- [Delete VPC](#delete-vpc)

#### Delete RDS
1. Go to the RDS service, select the RDS instance you want to delete, choose Actions, and then select Delete.
   ![Clean RDS](/images/5-Clean-resources/clean_rds.jpg)
2. **Wait a moment for the RDS to be completely deleted.**

#### Delete EC2
1. Go to the EC2 service, select the EC2 instance you want to delete, choose Instance state, and then select Terminate (delete) instance.
   ![Clean EC2](/images/5-Clean-resources/clean_ec2.jpg)
2. **Wait a moment for the EC2 instance to be completely deleted.**

#### Delete VPC
1. Go to the VPC service, select the VPC you want to delete, choose Actions, and then select Delete VPC.
   ![Clean VPC](/images/5-Clean-resources/clean_vpc.jpg)
   {{% notice info %}}
   If the VPC cannot be deleted due to dependent resources, delete those dependent resources first, then try deleting the VPC again.
   {{% /notice %}}
