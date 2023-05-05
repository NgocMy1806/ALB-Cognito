---
title : "Launch EC2"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.5</b> "
---

1. Go to [EC2 management console](https://console.aws.amazon.com/ec2/v2/home) to create an instance.
  + Click **Instances**.
  + Click **Launch instances**.
  
![EC2](/images/2.prerequisite/011-1-ec2.png)

  + **Name** of the instance, enter **demo-ec2** 
  + Select AMI **Amazon Linux 2 AMI**.
  ![EC2](/images/2.prerequisite/011-ec2.png)
  + Select Instance type **t2.micro**.
  + Choose an existing key pair or create a new one.
  + **Network**, select **Demo-vpc**.
  + **Subnet**, select **Public Subnet1**.
  + **Auto-assign Public IP**, select **Enable**
    ![EC2](/images/2.prerequisite/012-ec2.png)
  + Select **Select an existing security group**.
  + Select **SG Public Linux Instance**.
  + Click **Launch Instance**.
  ![EC2](/images/2.prerequisite/013-ec2.png)

  After the instance is successfully launched, you can proceed to the next step to create a simple website on the EC2 instance.