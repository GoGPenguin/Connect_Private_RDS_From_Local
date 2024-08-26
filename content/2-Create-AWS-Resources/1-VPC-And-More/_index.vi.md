+++
title = "Tạo VPC và các tài nguyên liên quan"
date = 2024
weight = 1
chapter = false
pre = "<b>2.1. </b>"
+++

{{% notice note %}}
Theo tổng quan kiến trúc và hướng dẫn thì mình sẽ tạo VPC bao gồm 2 AZ và 4 Subnets nhưng các bạn có thể tạo 1 AZ và 2 Subnets (1 public cho **EC2** và 1 private cho **RDS**)
{{% /notice %}}

## NỘI DUNG

- [NỘI DUNG](#nội-dung)
    - [Tạo VPC](#tạo-vpc)
    - [Tạo Subnets](#tạo-subnets)
    - [Tạo Internet Gateway](#tạo-internet-gateway)
    - [Tạo Security Groups](#tạo-security-groups)
    - [Tạo Route Table](#tạo-route-table)

#### Tạo VPC
1. Tìm kiếm VPC trên thanh tìm kiếm và chọn vào dịch vụ **VPC**. Màn hình VPC Dashboard:
![VPC Dashboard](/images/1-VPC-And-More/vpc_console.jpg?width=1200px)

2. Chọn **Your VPCs** để vào màn hình quản lý các VPCs:  
*Hiện tại chưa có VPC nào được tạo*  
Nhấn chọn **Create VPC**
![VPC Manage](/images/1-VPC-And-More/vpc_dashboard.jpg?width=1200px)

3. Chọn VPC Only và điền các thông tin như hình, sau đó chọn **Create VPC**
![VPC Manage](/images/1-VPC-And-More/vpc_create.jpg?width=1000px)

Ra ngoài giao diện các bạn sẽ thấy đã tạo VPC thành công

#### Tạo Subnets
1. Chọn mục **Subnets** ở sidebar VPC Dashboard, để vào màn hình quản lý subnets và chọn **Create subnet**:
![Subnets Manage](/images/1-VPC-And-More/subnet_console.jpg?width=1400px)
1. Chọn VPC và điền/chọn các thông tin cần thiết (name, AZ, CIDR block):  

***Ví dụ thông tin của 1 public subnet ở AZ ap-southeast-1a***
![Subnets Manage](/images/1-VPC-And-More/subnet_01.jpg?width=1400px)

{{% notice note %}}
Các subnet sau thay đổi thông tin của AZ (**có thể tùy chỉnh**), ví dụ:  
**Name:** public_subnet_2, **AZ:** ap-southeast-1b, **CIDR:** 10.0.1.0/24  
**Name:** private_subnet_1, **AZ:** ap-southeast-1a, **CIDR:** 10.0.2.0/24**  
**Name:** private_subnet_2, **AZ:** ap-southeast-1b, **CIDR:** 10.0.3.0/24**  
{{% /notice %}}

Sau khi review lại và nhấn **Create subnet** sẽ tạo thành công.

#### Tạo Internet Gateway
{{% notice info %}}
IGW là tài nguyên cho phép truy cập ra ngoài internet.
{{% /notice %}}
1. Chọn mục **Internet gateways** ở sidebar VPC Dashboard, để vào màn hình quản lý subnets và chọn **Create internet gateway**:
![IGW Console](/images/1-VPC-And-More/igw_console.jpg?width=1400px)
2. Đặt tên và nhấn **Create internet gateway** sẽ tạo thành công:
![IGW Console](/images/1-VPC-And-More/create_igw.jpg?width=1400px)
3. Xem thông tin về IGW vừa tạo, nhấn **Attach to VPC** để gắn IGW vừa tạo vào VPC đã tạo trước đó:
![IGW Console](/images/1-VPC-And-More/igw_detail.jpg?width=1400px)
![IGW Console](/images/1-VPC-And-More/attach_igw_to_vpc.jpg?width=1400px)
Nhấn **Attach internet gateway** sẽ gắn thành công vào VPC.

#### Tạo Security Groups
1. Tiếp tục chọn **Security groups** ở sidebar để vào màn hình quản lý Security group, sau đó nhấn chọn Create security group:
![SG Console](/images/1-VPC-And-More/sgs_console.jpg?width=1400px)
2. Đặt tên, chọn VPC đã tạo và tạo inbound rules của *Public Security Group* cho Public Subnet:
![SG Console](/images/1-VPC-And-More/public_sgs_detail.jpg?width=1400px)
3. Tương tự, chỉ thay đổi inbounds rules với *Private Security Group* cho Private Subnet:
![SG Console](/images/1-VPC-And-More/private_sgs_detail.jpg?width=1400px)

#### Tạo Route Table
1. Chọn mục **Route tables** ở sidebar VPC Dashboard, để vào màn hình quản lý subnets và chọn **Create route table**:
![Route table Manage](/images/1-VPC-And-More/route_table_console.jpg?width=1400px)
2. Tạo Public route table:
![Route table Manage](/images/1-VPC-And-More/create_public_route.jpg?width=1400px)
Nhấn **Create route table**
![Route table Manage](/images/1-VPC-And-More/public_route_detail.jpg?width=1400px)
Chỉnh sửa public route để có thể định tuyến ra internet (Chọn route table cần chỉnh sửa và chọn mục **Routes**)  
![Route table Manage](/images/1-VPC-And-More/public_route_igw.jpg?width=1400px)
Nhấn **Save changes**.

{{% notice note %}}
Ở bài này chưa cần tạo private table cho private subnet
{{% /notice %}}