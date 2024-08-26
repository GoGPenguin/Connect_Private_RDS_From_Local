+++
title = "Tạo RDS"
date = 2024
weight = 2
chapter = false
pre = "<b>2.3. </b>"
+++

{{% notice note %}}
Phần này chúng ta sẽ khởi tạo Postgre RDS ở private subnet
{{% /notice %}}

#### Các bước tiến hành

1. Trên thanh tìm kiếm tìm dịch vụ **RDS** và chọn để vào giao diện dashboard:
   ![DB SG](../../../images/3-RDS/rds_console.jpg)
2. Chọn Subnets groups ở sidebar và nhấn **Create DB subnet group**
   ![DB SG](../../../images/3-RDS/rds_subnet_gr.jpg)
3. Điền các thông tin cần thiết, chọn VPC và **private subnet** sau đó nhấn **Create**
   ![DB SG](../../../images/3-RDS/rds_subnet_gr_create.jpg)

{{% notice note %}}
Nhớ điền description nếu không sẽ báo lỗi
{{% /notice %}}
Tạo thành công DB subnet group
![DB SG](../../../images/3-RDS/rds_subnet_gr_success.jpg) 4. Chọn **Databases** ở sidebar và nhấn **Create database** để tạo RDS  
_Thực hiện theo các bước (optional)_
![DB SG](../../../images/3-RDS/db_console.jpg)
![DB SG](../../../images/3-RDS/db_engine_opt.jpg)
![DB SG](../../../images/3-RDS/db_general_setting.jpg)
![DB SG](../../../images/3-RDS/db_default_1.jpg)
![DB SG](../../../images/3-RDS/db_connect_setting_01.jpg)
![DB SG](../../../images/3-RDS/db_connect_setting_02.jpg)
{{% notice warning %}}
Nhớ xem kỹ phần tính tiền trước khi tạo
{{% /notice %}}
![DB SG](../../../images/3-RDS/costs.jpg)
Xem lại thông tin và nhấn **Create database**:
Đợi 1 lúc để RDS có thể tạo thành công, sau đó **Lưu lại RDS endpoint** để dùng cho kết nối.
![DB SG](../../../images/3-RDS/rds_waiting_create.jpg)
![DB SG](../../../images/3-RDS/rds_endpoint.jpg)
Đã khởi tạo xong RDS.
