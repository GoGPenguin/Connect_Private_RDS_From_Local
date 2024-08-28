+++
title = "Yêu cầu"
date = 2024
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

**Nội dung:**

- [Có tài khoản AWS](#có-tài-khoản-aws)
- [Sử dụng IAM Account để làm lab (Nên làm)](#sử-dụng-iam-account-để-làm-lab-nên-làm)
- [Đã cài đặt AWS CLI](#đã-cài-đặt-aws-cli)
- [Cài đặt MobaXTerm](#cài-đặt-mobaxterm)
- [Cài đặt Laragon hoặc các phần mềm SQL UI (xampp,... ) tùy theo cơ sở dữ liệu mình chọn](#cài-đặt-laragon-hoặc-các-phần-mềm-sql-ui-xampp--tùy-theo-cơ-sở-dữ-liệu-mình-chọn)
- [Đã cài đặt Session Manager Plugin](#đã-cài-đặt-session-manager-plugin)

#### Có tài khoản AWS

1. Đi đến trang [Amazon Web Service homepage](https://aws.amazon.com/).
2. Chọn **Sign In to the Console** ở góc trên bên phải.
   - **\*Ghi Chú:** Có thể là **Create an AWS Account**.\*
3. Nhập thông tin tài khoảng và chọn **Continue**.
   - **\*Quan Trọng**: Hãy chắc chắn bạn nhập đúng thông tin, đặc biệt là email.\*
4. Chọn loại account.
   - **\*Ghi chú**: Personal và Professional đều có chung tính năng.\*
5. Nhập thông tin công ty hoặc thông tin cá nhân của bạn.
6. Đọc và đồng ý [AWS Customer Agreement](https://aws.amazon.com/agreement/).
7. Chọn **Create Account** và **Continue**.

#### Sử dụng IAM Account để làm lab (Nên làm)

{{% notice info %}}
Nếu đã dùng IAM Account thì có thể bỏ qua bước này
{{% /notice %}}

- Trong thanh tìm kiếm gõ **IAM** và chọn **IAM** sau đó chọn vào Users.
- Nếu chưa tồn tại User thì chọn **Create user**
- Điền thông tin , chọn ô **Provide user access to the AWS Management Console - optional** sau đó nhấn **Next**.
- Ở mục **Attach policies directly** tìm kiếm **\*AdministratorAccess** và chọn sau đó tiếp tục **Next**.
- Xem lại các thông tin và nhấn **Create user**.
- Nhận tài khoản, mật khẩu, Console sign-in URL (có thể lưu lại) và dùng các thông tin để đăng nhập bằng IAM User.

{{% notice note %}}
Tạo **Access key** cho user để có thể đăng nhập bằng CLI. (Chọn User cần tạo, vào mục **Access key** trong **Security credentials**)
{{% /notice %}}

#### Đã cài đặt AWS CLI

Link hướng dẫn cài đặt và kiểm tra [Install AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

#### Cài đặt MobaXTerm

#### Cài đặt Laragon hoặc các phần mềm SQL UI (xampp,... ) tùy theo cơ sở dữ liệu mình chọn

#### Đã cài đặt Session Manager Plugin

Link hướng dẫn cài đặt và kiểm tra [Install Session Manager Plugin](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-working-with-install-plugin.html)
