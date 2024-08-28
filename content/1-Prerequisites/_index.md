+++
title = "Prerequisites"
date = 2024
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

**Content:**

- [Have an AWS Account](#have-an-aws-account)
- [Use an IAM Account for the Lab (Recommended)](#use-an-iam-account-for-the-lab-recommended)
- [AWS CLI Installed](#aws-cli-installed)
- [MobaXTerm Installed](#mobaxterm-installed)
- [Install Laragon or other SQL UI software (XAMPP, etc.) depending on the database you choose](#install-laragon-or-other-sql-ui-software-xampp-etc-depending-on-the-database-you-choose)
- [Session Manager Plugin Installed](#session-manager-plugin-installed)

#### Have an AWS Account

1. Go to the [Amazon Web Service homepage](https://aws.amazon.com/).
2. Click on **Sign In to the Console** at the top right corner.
   - **\*Note:** You may need to click **Create an AWS Account** instead.\*
3. Enter your account information and select **Continue**.
   - **\*Important**: Make sure to enter accurate information, especially your email address.\*
4. Choose your account type.
   - **\*Note**: Both Personal and Professional accounts have the same features.\*
5. Enter your company or personal information.
6. Read and agree to the [AWS Customer Agreement](https://aws.amazon.com/agreement/).
7. Select **Create Account** and **Continue**.

#### Use an IAM Account for the Lab (Recommended)

{{% notice info %}}
If you are already using an IAM Account, you can skip this step.
{{% /notice %}}

- In the search bar, type **IAM** and select **IAM**, then go to Users.
- If the User does not exist, select **Create user**.
- Enter the information, check the box **Provide user access to the AWS Management Console - optional**, and then click **Next**.
- In the **Attach policies directly** section, search for **\*AdministratorAccess** and select it, then continue with **Next**.
- Review the information and click **Create user**.
- Obtain the account details, password, and Console sign-in URL (you may save this information) and use these credentials to log in with the IAM User.

{{% notice note %}}
Create an **Access key** for the user to enable CLI login. (Select the user, go to the **Access key** section in **Security credentials**)
{{% /notice %}}

#### AWS CLI Installed

Installation and setup guide: [Install AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

#### MobaXTerm Installed

#### Install Laragon or other SQL UI software (XAMPP, etc.) depending on the database you choose

#### Session Manager Plugin Installed

Installation and setup guide: [Session Manager Plugin](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-working-with-install-plugin.html)
