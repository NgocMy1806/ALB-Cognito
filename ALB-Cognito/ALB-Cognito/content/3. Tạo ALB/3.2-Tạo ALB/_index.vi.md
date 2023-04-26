---
title : "Tạo ALB"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2. </b> "
---

1. Truy cập vào [giao diện quản trị của dịch vụ EC2](https://console.aws.amazon.com/ec2/v2/home).
  + Click chọn **Load balancer**.
  + Click chọn **Create load balancer**.
![ALB](/images/3.alb/005-alb.png)

2. Tại màn hình tạo Load Balancer
  + Click chọn **create Application Load Balancer**.
![ALB](/images/3.alb/006-alb.png)
  + Tại mục **Load balancer name**, nhập **demo-cognito**.
  + Tại mục **VPC**, chọn **Demo-vpc**.
![ALB](/images/3.alb/007-alb.png)
  + Tại mục **Mappings**, tick chọn 2 AZ. Vì trong mỗi AZ, chúng ta chỉ tạo 1 public subnet, cho nên ko cần chọn subnet nữa.
  + Tại mục **Security groups**, chọn **SG ALB**.
![ALB](/images/3.alb/008-alb.png)
  + Tại mục **Listeners and routing**, chọn protocol **HTTPS**, trong **Default actions** chọn **demo-cognito**.
  + Tại mục **Default SSL/TLS certificate**, chọn certificate đã request bằng ACM.
![ALB](/images/3.alb/009-alb.png)
  + Cuộn xuống cuối trang và click button **Create load balancer**

3. Hoàn thành tạo Load Balancer

Quá trình tạo Load Balancer sẽ mất khoảng 5-10 phút để hoàn thành. Bạn có thể kiểm tra sự thay đổi trạng thái từ provisioning sang active ở màn hình danh sách Load Balancer.

Sau khi ALB đã active, bạn hãy tick vào ALB, rồi sao chép **DNS name** của Load Balancer.
![ALB](/images/3.alb/010-alb.png)

4. Tạo CNAME record trỏ đến ALB
Để
Truy cập bằng cách dán DNS name vào trình duyệt. 

