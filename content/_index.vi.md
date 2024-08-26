+++
title = "Kết nối RDS từ máy tính local thông qua EC2 với Session Manager"
date = 2024
weight = 0
pre = "<b>0. </b>"
chapter = false
+++

# Kết nối RDS thông qua EC2

#### Tổng quan

Trong bài lab này, bạn sẽ kết nối được **RDS** trong private subnet thông qua **EC2** instance ở public subnet bằng **Session Manager**

#### RDS (Relational Database Service)

**RDS**  là một dịch vụ cơ sở dữ liệu quan hệ được quản lý của AWS. Nó giúp bạn thiết lập, vận hành và mở rộng các cơ sở dữ liệu quan hệ trên đám mây một cách dễ dàng.

{{% notice info %}}
Với RDS, bạn có thể sử dụng các hệ quản trị cơ sở dữ liệu phổ biến như MySQL, PostgreSQL, MariaDB, Oracle Database, và Microsoft SQL Server.
{{% /notice %}}

#### EC2 (Elastic Compute Cloud)

**EC2** là một dịch vụ điện toán đám mây của AWS, cho phép bạn tạo và quản lý các máy chủ ảo (instances) trên đám mây. Với EC2, bạn có thể dễ dàng mở rộng hoặc giảm tải các tài nguyên máy tính theo nhu cầu, mà không cần đầu tư vào phần cứng thực tế.

#### Session Manager

**Session Manager** là một công cụ quản lý phiên làm việc trong AWS Systems Manager, cho phép bạn quản lý và truy cập các instance EC2 từ xa mà không cần mở cổng SSH hoặc RDP

{{% notice info %}}
Session Manager là một giải pháp an toàn và hiệu quả để quản lý các instance trong môi trường AWS.
{{% /notice %}}


#### Nội dung chính

1. [Yêu cầu](1-Prerequisites/)
2. [Tạo các tài nguyên AWS](2-Create-AWS-Resources/)
3. [Kết nối tới RDS](3-Connect-To-RDS/)
4. [Dọn dẹp tài nguyên](4-Clean-Resources/)
