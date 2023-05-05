---
title : "Create security group"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.4</b> "
---

#### Create security groups

In this step, we will create security groups for the ALB and instances.

#### Create security group for ALB

1. Access the [VPC service management interface](https://console.aws.amazon.com/vpc)
  + Click **Security Group**.  
  + Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

2. At the **Create security group** screen
  + **Security group name**, enter **SG ALB**. 
  + **Description**, enter **SG ALB**.
  + **VPC**, click **X** icon to select the **Demo-vpc** you created for this lab.

![SG](/images/2.prerequisite/007-createsgalb.png)

3. Configure the **Inbound rule** 
  + As we have successfully requested an SSL certificate for the domain, we can restrict connections from the internet to the ALB only through the HTTPS protocol, port 443.
  ![SG](/images/2.prerequisite/008-createsgalb.png)

4. Check  **Outbound rule**, then click **Create security group**.

#### Create security group for Linux instance in public subnet

1. Access the [VPC service management interface](https://console.aws.amazon.com/vpc)
  + Click **Security Group**.  
  + Click **Create security group**.

![SG](/images/2.prerequisite/019-createsg.png)

2. At the **Create security group** screen
  + **Security group name**, enter **SG Public Linux Instance**. 
  + **Description**, enter **SG Public Linux Instance**.
  + **VPC**, click **X** icon to select the **Demo-vpc** you created for this lab.

![SG](/images/2.prerequisite/009-createec2sg.png)

3. Configure the **Inbound rule** 
  + The EC2 instance does not receive traffic directly from users but through the ALB, so we will configure the inbound rule to allow traffic only through the HTTP protocol, port 80 from the source Security group of the ALB.
  ![SG](/images/2.prerequisite/010-createec2sg.png)

4. Check  **Outbound rule**, then click **Create security group**.

    So we have created the necessary security groups for the EC2 instances and ALB.