+++
title = "Create RDS"
date = 2024
weight = 2
chapter = false
pre = "<b>2.3. </b>"
+++

{{% notice note %}}
In this section, we will create a PostgreSQL RDS in the private subnet.
{{% /notice %}}

#### Steps to Follow

1. In the search bar, type **RDS** and select it to access the dashboard:
   ![DB SG](../../../images/3-RDS/rds_console.jpg)
2. Select Subnet Groups from the sidebar and click **Create DB subnet group**.
   ![DB SG](../../../images/3-RDS/rds_subnet_gr.jpg)
3. Fill in the necessary details, select the VPC and **private subnet**, then click **Create**.
   ![DB SG](../../../images/3-RDS/rds_subnet_gr_create.jpg)

{{% notice note %}}
Remember to fill in the description; otherwise, you'll get an error.
{{% /notice %}}
The DB subnet group is created successfully.
![DB SG](../../../images/3-RDS/rds_subnet_gr_success.jpg) 4. Select **Databases** from the sidebar and click **Create database** to create the RDS instance.  
_Proceed with the steps (optional):_
![DB SG](../../../images/3-RDS/db_console.jpg)
![DB SG](../../../images/3-RDS/db_engine_opt.jpg)
![DB SG](../../../images/3-RDS/db_general_setting.jpg)
![DB SG](../../../images/3-RDS/db_default_1.jpg)
![DB SG](../../../images/3-RDS/db_connect_setting_01.jpg)
![DB SG](../../../images/3-RDS/db_connect_setting_02.jpg)
{{% notice warning %}}
Be sure to review the cost details before creating the RDS instance.
{{% /notice %}}
![DB SG](../../../images/3-RDS/costs.jpg)
Review the information and click **Create database**:
Wait a moment for the RDS instance to be created successfully, then **Save the RDS endpoint** for use in the connection.
![DB SG](../../../images/3-RDS/rds_waiting_create.jpg)
![DB SG](../../../images/3-RDS/rds_endpoint.jpg)
RDS has been successfully created.
