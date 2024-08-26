+++
title = "Kết nối tới RDS từ máy local thông qua EC2"
date = 2024
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

Ở bước này chúng ta sẽ kết nối RDS trên AWS ở máy tính cá nhân (local)

1. Kiểm tra kết nối từ EC2 tới RDS
- SSH vào EC2 Instance kiểm tra đã cài đặt ssm-agent, postgres-client
![DB SG](/images/4-Connect-RDS/amazon-ssm-agent_success.jpg)
- Kiểm tra kết nối tới RDS bằng câu lệnh  
`psql -h <rds-endpoint> -U <username> --password`
- Sau đó điền password lúc khởi tạo RDS, nếu thành công sẽ có giao diện như sau:
![DB SG](/images/4-Connect-RDS/rds_connect_ec2.jpg)
2. Sử dụng cmd/powershell/git bash để đăng nhập vào account AWS bằng Access key (file .pem) đã tạo và lưu ở đầu bài. 
3. Sử dụng Port forward để mở 1 port trên máy local kết nối tới RDS thông qua EC2 bằng câu lệnh:  
`aws ssm start-session --region <resources-region> `  
`target <ec2-instance-id> ^`  
`document-name AWS-StartPortForwardingSessionToRemoteHost `  
`parameters host="<rds-endpoint>",portNumber="<rds-port-number>",localPortNumber="<local-port-number>"`
{{% notice warning %}}
4 dòng trên là 1 câu lệnh  
{{% /notice %}}
![DB SG](/images/4-Connect-RDS/sso_rds.jpg)
Có dòng **Waiting to connect** chứng tỏ rds đã sẵn sàng để kết nối.
{{% notice info %}}
1 số terminal không hiện dòng **Waiting to connect**, nhưng connect vào vẫn được
{{% /notice %}}

4. Mở Laragon và chọn/điền các thông tin để kết nối tới RDS. Sau đó nhấn Open
- Laragon dashboard
![DB SG](/images/4-Connect-RDS/laragon_console.jpg)
- Các thông tin cài đặt
![DB SG](/images/4-Connect-RDS/laragon_db_detail.jpg)
{{% notice note %}}
User và Password là các thông tin đã điền khi khởi tạo RDS
Port là local port đã mở để kết nối
{{% /notice %}}

5. Ở terminal thông báo kết nối thành công tới RDS từ máy tính Local. 
![DB SG](/images/4-Connect-RDS/connect_success_cli.jpg)
6. Một giao diện sẽ hiển thị sau khi thành công, chúng ta có thể query từ giao diện này.
![DB SG](/images/4-Connect-RDS/connect_success.jpg)

Chúng ta đã hoàn thành bài lab kết nối RDS từ máy tính local thông qua EC2 và Session Manager
