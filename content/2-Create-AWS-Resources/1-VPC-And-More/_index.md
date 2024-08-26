+++
title = "Create VPC and Related Resources"
date = 2024
weight = 1
chapter = false
pre = "<b>2.1. </b>"
+++

{{% notice note %}}
According to the architecture overview and guide, we will create a VPC with 2 Availability Zones (AZ) and 4 Subnets. However, you can create 1 AZ with 2 Subnets (1 public for **EC2** and 1 private for **RDS**).
{{% /notice %}}

## CONTENT

- [CONTENT](#content)
    - [Create VPC](#create-vpc)
    - [Create Subnets](#create-subnets)
    - [Create Internet Gateway](#create-internet-gateway)
    - [Create Security Groups](#create-security-groups)
    - [Create Route Table](#create-route-table)

#### Create VPC

1. Search for VPC in the search bar and select the **VPC** service. The VPC Dashboard will appear:
   ![VPC Dashboard](../../images/1-VPC-And-More/vpc_console.jpg?width=1200px)

2. Select **Your VPCs** to enter the VPC management screen:  
   _Currently, no VPCs have been created._  
   Click **Create VPC**
   ![VPC Manage](../../images/1-VPC-And-More/vpc_dashboard.jpg?width=1200px)

3. Choose VPC Only, fill in the details as shown, and then select **Create VPC**
   ![VPC Manage](../../images/1-VPC-And-More/vpc_create.jpg?width=1000px)

You will see the VPC has been successfully created.

#### Create Subnets

1. Select **Subnets** in the VPC Dashboard sidebar to enter the subnet management screen, and click **Create subnet**:
   ![Subnets Manage](../../images/1-VPC-And-More/subnet_console.jpg?width=1400px)
1. Select the VPC and enter/select the necessary details (name, AZ, CIDR block):

**_Example details for a public subnet in AZ ap-southeast-1a_**
![Subnets Manage](../../images/1-VPC-And-More/subnet_01.jpg?width=1400px)

{{% notice note %}}
For the following subnets, change the AZ information (**you can customize it**), for example:  
**Name:** public_subnet_2, **AZ:** ap-southeast-1b, **CIDR:** 10.0.1.0/24  
**Name:** private_subnet_1, **AZ:** ap-southeast-1a, **CIDR:** 10.0.2.0/24\*\*  
**Name:** private_subnet_2, **AZ:** ap-southeast-1b, **CIDR:** 10.0.3.0/24\*\*  
{{% /notice %}}

After reviewing, click **Create subnet** to successfully create it.

#### Create Internet Gateway

{{% notice info %}}
An IGW (Internet Gateway) is a resource that allows access to the internet.
{{% /notice %}}

1. Select **Internet gateways** in the VPC Dashboard sidebar to enter the IGW management screen, and click **Create internet gateway**:
   ![IGW Console](../../images/1-VPC-And-More/igw_console.jpg?width=1400px)
2. Name it and click **Create internet gateway** to successfully create it:
   ![IGW Console](../../images/1-VPC-And-More/create_igw.jpg?width=1400px)
3. View the information about the newly created IGW, click **Attach to VPC** to attach the IGW to the previously created VPC:
   ![IGW Console](../../images/1-VPC-And-More/igw_detail.jpg?width=1400px)
   ![IGW Console](../../images/1-VPC-And-More/attach_igw_to_vpc.jpg?width=1400px)
   Click **Attach internet gateway** to successfully attach it to the VPC.

#### Create Security Groups

1. Continue by selecting **Security groups** in the sidebar to enter the Security Group management screen, then click **Create security group**:
   ![SG Console](../../images/1-VPC-And-More/sgs_console.jpg?width=1400px)
2. Name it, select the created VPC, and set up inbound rules for the _Public Security Group_ for the Public Subnet:
   ![SG Console](../../images/1-VPC-And-More/public_sgs_detail.jpg?width=1400px)
3. Similarly, change only the inbound rules for the _Private Security Group_ for the Private Subnet:
   ![SG Console](../../images/1-VPC-And-More/private_sgs_detail.jpg?width=1400px)

#### Create Route Table

1. Select **Route tables** in the VPC Dashboard sidebar to enter the Route Table management screen, and click **Create route table**:
   ![Route table Manage](../../images/1-VPC-And-More/route_table_console.jpg?width=1400px)
2. Create a Public route table:
   ![Route table Manage](../../images/1-VPC-And-More/create_public_route.jpg?width=1400px)
   Click **Create route table**
   ![Route table Manage](../../images/1-VPC-And-More/public_route_detail.jpg?width=1400px)
   Edit the public route to enable internet routing (Select the route table to edit and choose the **Routes** section)  
   ![Route table Manage](../../images/1-VPC-And-More/public_route_igw.jpg?width=1400px)
   Click **Save changes**.

{{% notice note %}}
In this lab, there is no need to create a private route table for the private subnet.
{{% /notice %}}
