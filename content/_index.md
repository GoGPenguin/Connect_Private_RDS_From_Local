+++
title = "Connecting to RDS via EC2 with Session Manager"
date = 2024
weight = 0
pre = "<b>0. </b>"
chapter = false
+++

# Connecting to RDS via EC2

#### Overview

In this lab, you will connect to an **RDS** in a private subnet through an **EC2** instance in a public subnet using **Session Manager**.

#### RDS (Relational Database Service)

**RDS** is a managed relational database service by AWS. It helps you easily set up, operate, and scale relational databases in the cloud.

{{% notice info %}}
With RDS, you can use popular database engines such as MySQL, PostgreSQL, MariaDB, Oracle Database, and Microsoft SQL Server.
{{% /notice %}}

#### EC2 (Elastic Compute Cloud)

**EC2** is a cloud computing service by AWS that allows you to create and manage virtual servers (instances) in the cloud. With EC2, you can easily scale up or down your computing resources based on demand, without the need for physical hardware investment.

#### Session Manager

**Session Manager** is a session management tool within AWS Systems Manager, enabling you to remotely manage and access EC2 instances without opening SSH or RDP ports.

{{% notice info %}}
Session Manager is a secure and efficient solution for managing instances in an AWS environment.
{{% /notice %}}

#### Main Content

1. [Prerequisites](1-Prerequisites/)
2. [Create AWS Resources](2-Create-AWS-Resources/)
3. [Connect to RDS](3-Connect-To-RDS/)
4. [Clean Up Resources](4-Clean-Resources/)
