---
title : "ALB Authentication rule"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---
1. Open the Load Balancer management screen, select **demo-cognito**
 ![Cognito](/images/4.cognito/017-alb-cognito.png)
- Tick the listener **HTTPS:443**, then click **Manage rules**
 ![Cognito](/images/4.cognito/018-alb-cognito.png)
- Click `+` icon to create new rule
 ![Cognito](/images/4.cognito/019-alb-cognito.png)
- Our goal is to configure ALB to route users to Cognito when they access the website with the path `/demo-cognito/dashboard.html`. After authentication, ALB will allow the user to access the requested website in the EC2. To do this, we will configure as follows:
- Click **Add condition**, select **Path**
- **Path**, enter **/demo-cognito/dashboard.html**
- Click **Add action**, select **Authenticate…**
- **Authenticate,** select **Amazon Cognito**.
- **Cognito user pool,** select ID of user pool demo-cognito.
- **App client,** select the ID of the app client  **demo cognito**.
- **Session timeout**, enter 180
{{% notice info %}}
You can leave the Session timeout value as default. Changing it to 180s is only for testing purposes. The reason will be explained in more detail in section 5. `Check result`
{{% /notice %}}

 ![Cognito](/images/4.cognito/020-alb-cognito.png)

- Click `✔ ` icon to complete creating the action that routes to Cognito.
- Click **Add action**, select **Forward to**
 ![Cognito](/images/4.cognito/021-alb-cognito.png)
- **Target group**, select **demo-cognito**
- Click `✔ ` icon to complete creating the action that routes to target group after the user has been authenticated by Cognito.
- Click  **Save** to save the configuration of the rule.
 ![Cognito](/images/4.cognito/022-alb-cognito.png)

    Now we have completed configuring ALB and Cognito.



