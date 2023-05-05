---
title : "Create ALB"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2. </b> "
---

1.Access the [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home).
  + Click **Load balancer**.
  + Click **Create load balancer**.
![ALB](/images/3.alb/005-alb.png)

2. At the load balancer creation screen
  + Click **create Application Load Balancer**.
![ALB](/images/3.alb/006-alb.png)
  + **Load balancer name**, enter **demo-cognito**.
  + **VPC**, select **Demo-vpc**.
![ALB](/images/3.alb/007-alb.png)
  + **Mappings**, select 2 AZs. Since we have only created 1 public subnet in each AZ, there is no need to select subnet.
  + **Security groups**, select **SG ALB**.
![ALB](/images/3.alb/008-alb.png)
  + **Listeners and routing**, select protocol **HTTPS**, in **Default actions**, select **demo-cognito**.
  + **Default SSL/TLS certificate**, select the certificate that was requested using ACM.
![ALB](/images/3.alb/009-alb.png)
  + Scroll down to the bottom of the page and click **Create load balancer**

3. Finish creating the Load Balancer

    The process of creating the Load Balancer will take around 5-10 minutes to complete. You can check the status change from provisioning to active on the Load Balancer list screen.

    After the ALB is active, tick the ALB, and then copy the **DNS name** of the Load Balancer.
![ALB](/images/3.alb/010-alb.png)

4. Create a CNAME record pointing to ALB

    Next, we will configure Route 53 to route demo-cog.mymy.asia domain to the DNS of the ALB.
  + Access the [Route53 service management console.](https://console.aws.amazon.com/route53/v2/home).
  + Click **Hosted zones**.
  + Select the created Hosted zone.
![ALB](/images/3.alb/011-alb.png)
  + Click **Create record**
![ALB](/images/3.alb/012-alb.png)
  + **Record name**, enter **demo-cognito**.
  {{% notice info %}}
  If you want to point the root domain directly to ALB, you can leave this field blank.
  {{% /notice %}}
  + **Record type**, select **A**.
  + ON toggle **Alias**.
  + **Value**, enter DNS of ALB.
  + Click **Create records**
![ALB](/images/3.alb/013-alb.png)

    After successfully creating the record, paste the **record name** of the newly created record into your browser's address bar.
    You will see the default apache screen.
  ![ALB](/images/3.alb/014-alb.png)
    To check the website that we have created, you need to add `/demo-cognito/` to the URL (as we have created the website html files in this folder).
  ![ALB](/images/3.alb/015-alb.png)

    You can see that at this time, we can freely access all pages (index, dashboard, logged_out) without logging in.
    We will proceed to configure the authentication process in the next step. 


