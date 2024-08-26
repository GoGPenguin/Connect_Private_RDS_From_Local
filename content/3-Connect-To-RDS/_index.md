+++
title = "Connect to RDS from Local Machine through EC2"
date = 2024
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

In this step, we will connect to the RDS on AWS from a personal (local) computer.

1. Verify the connection from EC2 to RDS:

   - SSH into the EC2 instance and check if ssm-agent and postgres-client are installed.
     ![DB SG](../images/4-Connect-RDS/amazon-ssm-agent_success.jpg)
   - Test the connection to RDS using the command:  
     `psql -h <rds-endpoint> -U <username> --password`
   - Enter the password set during RDS creation. If successful, you will see the following screen:
     ![DB SG](../images/4-Connect-RDS/rds_connect_ec2.jpg)

2. Use `cmd`, `PowerShell`, or `Git Bash` to log in to the AWS account using the Access key (the `.pem` file) created and saved earlier in the guide.

3. Use port forwarding to open a local port that connects to the RDS through EC2 with the following command:  
   `aws ssm start-session --region <resources-region> `  
   `--target <ec2-instance-id> ^`  
   `--document-name AWS-StartPortForwardingSessionToRemoteHost `  
   `--parameters host="<rds-endpoint>",portNumber="<rds-port-number>",localPortNumber="<local-port-number>"`
   {{% notice warning %}}
   The four lines above form a single command.
   {{% /notice %}}
   ![DB SG](../images/4-Connect-RDS/sso_rds.jpg)
   Seeing **Waiting to connect** indicates that the RDS is ready to connect.
   {{% notice info %}}
   Some terminals may not show **Waiting to connect**, but the connection can still be successful.
   {{% /notice %}}

4. Open Laragon and select/enter the information to connect to the RDS. Then click Open.

   - Laragon dashboard:
     ![DB SG](../images/4-Connect-RDS/laragon_console.jpg)
   - Connection settings:
     ![DB SG](../images/4-Connect-RDS/laragon_db_detail.jpg)
     {{% notice note %}}
     The username and password are the credentials used when creating the RDS.  
     The port is the local port that was opened for the connection.
     {{% /notice %}}

5. The terminal will display a successful connection to the RDS from the local machine.
   ![DB SG](../images/4-Connect-RDS/connect_success_cli.jpg)

6. A user interface will appear upon success, allowing you to run queries.
   ![DB SG](../images/4-Connect-RDS/connect_success.jpg)

We have now completed the lab to connect to RDS from a local machine via EC2 and Session Manager.
