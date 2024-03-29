---
title : "Tạo security group"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.4</b> "
---

#### Tạo các security groups

Trong bước này chúng ta sẽ tiến hành tạo các security groups cho ALB và các instance. 

#### Tạo security group cho ALB 

1. Truy cập [giao diện quản trị dịch vụ VPC](https://console.aws.amazon.com/vpc)
  + Click **Security Group**.  
  + Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

3. Tại màn hình **Create security group**
  + Tại mục **Security group name**, điền **SG ALB**. 
  + Tại mục **Description**, điền **SG ALB**.
  + Tại mục **VPC**, click dấu **X** để chọn lại **Demo-vpc** bạn đã tạo cho bài lab này.

![SG](/images/2.prerequisite/007-createsgalb.png)

4. Cấu hình **Inbound rule** 
  + Vì chúng ta đã request thành công SSL certificate cho domain, vì vậy chúng ta có thể giới hạn chỉ cho phép kết nối từ internet vào ALB thông qua giao thức HTTPS, port 443
  ![SG](/images/2.prerequisite/008-createsgalb.png)

5. Giữ nguyên **Outbound rule**, kéo chuột xuống phía dưới.
  + Click **Create security group**.

#### Tạo security group cho Linux instance nằm trong public subnet 

1. Truy cập [giao diện quản trị dịch vụ VPC](https://console.aws.amazon.com/vpc)
  + Click **Security Group**.  
  + Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

3. Tại mục **Security group name**, điền **SG Public Linux Instance**. 
  + Tại mục **Description**, điền **SG Public Linux Instance**.
  + Tại mục **VPC**, click dấu **X** để chọn lại **Demo-vpc** bạn đã tạo cho bài lab này.

![SG](/images/2.prerequisite/009-createec2sg.png)

4. Cấu hình **Inbound rule** 
  + EC2 instance không nhận traffic trực tiếp từ user, mà nhận thông qua ALB, vì vậy, chúng ta sẽ cấu hình inbound rule chỉ cho phép nhận traffic thông qua giao thức http, port 80 từ source là Security group của ALB
  ![SG](/images/2.prerequisite/010-createec2sg.png)

5. Giữ nguyên **Outbound rule**, kéo chuột xuống phía dưới.
  + Click **Create security group**.

    Như vậy chúng ta đã tạo xong các security group cần thiết cho các EC2 instance và ALB.