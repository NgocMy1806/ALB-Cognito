---
title : "Create target group"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 3.1. </b> "
---

1. Access the [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home).
  + Click **Target Groups**.
  + Click **Create target groups**.
![TargetGroup](/images/3.alb/001-targetgr.png)

2. At the create target group screen:
  + **target type**, select **Instances**.
  + **Target group name**, enter **demo-cognito**.
  + **VPC**, enter **Demo-vpc**.
  + Scroll down to the bottom of the page and click **Next**.
![TargetGroup](/images/3.alb/002-targetgr.png)

2. At the register target screen:
  + Select the instance you just created.
  + Click **Include as pending below**(if not selected, accessing the DNS Load Balancer will result in an HTTP 503 error: Service unavailable).
  + Click **Create target group**.
![TargetGroup](/images/3.alb/003-targetgr.png)

3. Target group creation is complete.
![TargetGroup](/images/3.alb/004-targetgr.png)
