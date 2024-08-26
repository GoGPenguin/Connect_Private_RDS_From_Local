+++
title = "Tạo EC2 và IAM Role cho phép Session Manager quản lý"
date = 2024
weight = 2
chapter = false
pre = "<b>2.2. </b>"
+++

{{% notice note %}}
Phần này sẽ có 2 bước, đầu tiên là tạo **EC2** Intance ở public subnet và cài đặt các package cần thiết, sau đó là tạo **IAM Role** để gắn vào EC2 cho phép **Session Manager** có thể quản lý
{{% /notice %}}

- [Tạo EC2](#tạo-ec2)
- [Khởi tạo IAM Role](#khởi-tạo-iam-role)
- [Kiểm tra ở Session Manager](#kiểm-tra-ở-session-manager)

#### Tạo EC2

1. Trên thanh tìm kiếm tìm **EC2** và chọn để vào màn hình quản lý EC2. Sau đó nhấn **Launch instances** để khởi tạo
   ![EC2 Dashboard](../../../images/2-EC2/ec2_console.jpg)
2. Thực hiện theo các bước sau để khởi tạo cấu hình cho EC2  
   _Chọn cấu hình OS_
   ![EC2 Dashboard](../../../images/2-EC2/ec2_name_OS.jpg)
   _Khởi tạo keypair để SSH_
   ![EC2 Dashboard](../../../images/2-EC2/ec2_keypair.jpg)
   {{% notice warning %}}
   Lưu lại keypair để có thể SSH vào EC2
   {{% /notice %}}
   _Cấu hình network cho EC2_
   ![EC2 Dashboard](../../../images/2-EC2/ec2_network_setting.jpg)
   {{% notice note %}}
   EC2 ở public subnet, gắn public security group.
   {{% /notice %}}

Sau khi làm xong các bước trên thì xem lại thông tin và nhấn **Launch intance** để khởi tạo.
![EC2 Dashboard](../../../images/2-EC2/ec2_create_success.jpg)
**Chi tiết các thông tin của EC2**
![EC2 Dashboard](../../../images/2-EC2/ec2_detail.jpg)

3. Dùng MobaXTerm để thử kết nối SSH tới EC2 Instance vừa tạo
   ![EC2 Dashboard](../../../images/2-EC2/MobaXTerm.jpg)

4. Cài đặt amazon-ssm-agent bằng câu lệnh  
   `sudo yum install -y https://s3.amazonaws.com/ec2-downloads-windows/SSMAgent/latest/linux_amd64/amazon-ssm-agent.rpm`

5. Vì ở lab này chúng ta sẽ tạo Postgres RDS nên sẽ cài đặt postgres client  
   `sudo dnf install postgresql15.x86_64 -y`

#### Khởi tạo IAM Role

{{% notice note %}}
Trong chi tiết của EC2 đã tạo ở trên, chúng ta có thể thấy mục IAM Role vẫn còn trống. Bây giờ chúng ta sẽ tạo IAM Role.
{{% /notice %}}

1. Vào IAM chọn Role, sau đó chọn **Create role**.
2. Chọn theo hình và nhấn **Next**.
3. ![IAM Dashboard](../../../images/2-EC2/iam_ec2_role.jpg)
4. Tiếp tục **Next**.
   ![IAM Dashboard](../../../images/2-EC2/iam_ec2_role_permission.jpg)
5. Đặt tên và xem lại trước khi nhấn **Create role**.
   ![IAM Dashboard](../../../images/2-EC2/iam_ec2_role_review.jpg)
   IAM Role cho phép EC2 có thể quản lý bởi Session Manager đã được tạo thành công
   ![IAM Dashboard](../../../images/2-EC2/iam_ec2_role_success.jpg)
6. Quay lại EC2. Nhấn chọn EC2 cần quản lý, sau đó nhấn chuột phải chọn **Modify IAM role**
   ![IAM Dashboard](../../../images/2-EC2/ec2_modify_role_console.jpg)
7. Chọn Role vừa tạo và nhấn **Update IAM role**
   ![IAM Dashboard](../../../images/2-EC2/ec2_modify_role_detail.jpg)
   Thay đổi Role cho EC2 thành công
   ![IAM Dashboard](../../../images/2-EC2/ec2_modify_role_success.jpg)

#### Kiểm tra ở Session Manager

1. Ở thanh tìm kiếm gõ Session Manager, nhấn chọn **Start session**
   ![SSM Dashboard](../../../images/2-EC2/system_manager_start.jpg)
2. EC2 nếu đã được gắn quyền và cài đặt SSM-Agent thì sẽ hiển thị để cho phép quản lý
   ![SSM Dashboard](../../../images/2-EC2/system_manager_sso_0_instances.jpg)
