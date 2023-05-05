+++
title = "Clean up resources "
date = 2021
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

We will follow the following steps to delete the resources we created in this lab:

### Delete Load Balancer:

- Access **EC2 Management Console**
- On the left navigation pane, select **Load Balancers**
- Select **Load Balancer** related to the lab.
- Click **Actions**.
- Click **Delete**.

### Delete Target Group:

- Access **EC2 Management **Console**
- On the left navigation pane, select **Target Groups**
- Select **Target Group** related to the lab.
- CLick **Actions**.
- Select **Delete**.
- Click **Yes, delete**

### Delete instance

1. Access **EC2**
2. Click **Instances**
3. Select instance related to the lab.
4. Click  **Instance state**
5. Click  **Terminate instance**

### Delete Security group

1. Access **EC2**
2. Click **Security Group**
3. Select security groups related to the lab.
4. Click **Actions**
5. Click **Delete security group**

### Delete Keypair

1. Access **EC2**
2. Click **Key Pairs**
3. Click **Actions**
4. Click **Delete**

#### Delete User pool

1. Access Cognito
2. Select User pool
3. Click **Delete**

#### Delete VPC

1. Access **VPC**
2. Select **Your VPCs**
3. Select the VPCs related to the lab
4. Click **Actions**
5. Click **Delete VPC**


#### Delete Certificates 

1. Access **ACM**
2. Click **List certificates**
3. Select the VPCs related to the lab
4. Click **Delete**

#### Delete Hosted zone 

1. Access **Route 53** 
2. Select **Hosted zone**
3. Select the Hosted zone related to the lab
4. Click **Delete**