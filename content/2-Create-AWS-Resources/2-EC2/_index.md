+++
title = "Create EC2 and IAM Role for Session Manager Management"
date = 2024
weight = 2
chapter = false
pre = "<b>2.2. </b>"
+++

{{% notice note %}}
This section involves two steps: first, creating an **EC2** instance in the public subnet and installing the necessary packages, and second, creating an **IAM Role** to attach to the EC2 instance, allowing **Session Manager** to manage it.
{{% /notice %}}

- [Create EC2](#create-ec2)
- [Create IAM Role](#create-iam-role)
- [Check in Session Manager](#check-in-session-manager)

#### Create EC2

1. In the search bar, type **EC2** and select it to access the EC2 management screen. Then click **Launch instances** to start creating the instance.
   ![EC2 Dashboard](../../images/2-EC2/ec2_console.jpg)
2. Follow these steps to configure the EC2 instance:  
   _Select the OS configuration_
   ![EC2 Dashboard](../../images/2-EC2/ec2_name_OS.jpg)
   _Create a key pair for SSH_
   ![EC2 Dashboard](../../images/2-EC2/ec2_keypair.jpg)
   {{% notice warning %}}
   Save the key pair to SSH into the EC2 instance.
   {{% /notice %}}
   _Configure the network settings for EC2_
   ![EC2 Dashboard](../../images/2-EC2/ec2_network_setting.jpg)
   {{% notice note %}}
   The EC2 instance is in the public subnet, with the public security group attached.
   Auto-assign public IP choose Enable to allocate Public IP for EC2 instance.
   {{% /notice %}}

After completing the steps above, review the information and click **Launch instance** to create it.
![EC2 Dashboard](../../images/2-EC2/ec2_create_success.jpg)
**Details of the EC2 instance**
![EC2 Dashboard](../../images/2-EC2/ec2_detail.jpg)

3. Use MobaXTerm to test the SSH connection to the newly created EC2 instance.
   ![EC2 Dashboard](../../images/2-EC2/MobaXTerm.jpg)

4. Install the amazon-ssm-agent using the following command:  
   `sudo yum install -y https://s3.amazonaws.com/ec2-downloads-windows/SSMAgent/latest/linux_amd64/amazon-ssm-agent.rpm`

5. Since we will create a PostgreSQL RDS in this lab, install the PostgreSQL client:  
   `sudo dnf install postgresql15.x86_64 -y`

#### Create IAM Role

{{% notice note %}}
In the details of the EC2 instance created above, you'll notice the IAM Role section is still empty. Now, we'll create an IAM Role.
{{% /notice %}}

1. Go to IAM, select Role, then click **Create role**.
2. Follow the instructions and click **Next**.
3. ![IAM Dashboard](../../images/2-EC2/iam_ec2_role.jpg)
4. Continue with **Next**.
   ![IAM Dashboard](../../images/2-EC2/iam_ec2_role_permission.jpg)
5. Name the role and review before clicking **Create role**.
   ![IAM Dashboard](../../images/2-EC2/iam_ec2_role_review.jpg)
   The IAM Role that allows EC2 to be managed by Session Manager is now successfully created.
   ![IAM Dashboard](../../images/2-EC2/iam_ec2_role_success.jpg)
6. Go back to EC2. Select the EC2 instance you want to manage, right-click, and choose **Modify IAM role**.
   ![IAM Dashboard](../../images/2-EC2/ec2_modify_role_console.jpg)
7. Select the role you just created and click **Update IAM role**.
   ![IAM Dashboard](../../images/2-EC2/ec2_modify_role_detail.jpg)
   Successfully updated the IAM Role for the EC2 instance.
   ![IAM Dashboard](../../images/2-EC2/ec2_modify_role_success.jpg)

#### Check in Session Manager

1. In the search bar, type Session Manager, then click **Start session**.
   ![SSM Dashboard](../../images/2-EC2/system_manager_start.jpg)
2. If the EC2 instance has the appropriate permissions and the SSM-Agent installed, it will appear in the list for management.
   ![SSM Dashboard](../../images/2-EC2/system_manager_sso_0_instances.jpg)
