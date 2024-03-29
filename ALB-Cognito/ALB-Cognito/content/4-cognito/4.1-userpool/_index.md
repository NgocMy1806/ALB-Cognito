---
title : "Create user pool"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1. </b> "
---

1. Access the [Amazon Cognito management console](https://console.aws.amazon.com/cognito/v2/home).
  + Click **User pools**.
  + Click **Create user pools**.
![Cognito](/images/4.cognito/001-userpool.png)

2. At the **Configure sign-in experience** screen
  + **Cognito user pool sign-in options**, select **Email**.
  + Click **Next**.
![Cognito](/images/4.cognito/002-userpool.png)

3. At the **Configure security requirements** screen
  + **Password policy mode**, select **Custom**.
  + Uncheck all the **Password requirements** option.

  {{% notice info %}}
  You can use mode **Cognito defaults**, however, to avoid spending time creating complex passwords, this lab will use the custom policy mode.
  {{% /notice %}}
      ![Cognito](/images/4.cognito/003-userpool.png)
  + **MFA enforcement**, select **No MFA**.
  + Click **Next**.
![Cognito](/images/4.cognito/004-userpool.png)

4. At the **Configure sign-in experience** screen
  + Don't make any changes.
  + Click **Next**.


5. At the **Configure message delivery** screen
  + **Email provider**, select **Send email with Cognito**.
  + Click **Next**.
![Cognito](/images/4.cognito/005-userpool.png)

6. At the **Integrate your app** screen
  + **User pool name**, enter **demo-cognito**.
  + **Hosted authentication pages**, tick **Use the Cognito Hosted UI**.
  ![Cognito](/images/4.cognito/006-userpool.png)

  + **Domain type**, select **Use a Cognito domain**.
  + **Cognito domain**, enter the domain prefix you want.
  + **App type**, select **Public client**.
  + **App client name**, enter **demo-cognito**.
  ![Cognito](/images/4.cognito/007-userpool.png)
  + **Client secret**, select **Generate a client secret**.
  + **Allowed callback URLs**, enter **domain/oauth2/idpresponse**.
  {{% notice info %}}
   Replace the "domain" in the above URL with your own domain.
  {{% /notice %}}
![Cognito](/images/4.cognito/008-userpool.png)
  + Expand the **Advanced app client settings** section.
  + Scroll down to the **Allowed sign-out URLs** field, enter **domain/demo-cognito/logged_out.html**
  {{% notice info %}}
  Replace the "domain" in the above URL with your own domain.
  {{% /notice %}}
  + Click **Next**.
![Cognito](/images/4.cognito/009-userpool.png)

7. At the **Review and create** screen

    Double-check the information and then press **Create user pool**.
  ![Cognito](/images/4.cognito/010-userpool.png)

8. User pool creation is complete.

