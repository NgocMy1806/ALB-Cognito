---
title : "Register account"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 4.2. </b> "
---
+ Click on the user pool that you just created.

  ![Cognito](/images/4.cognito/011-testlogin.png)

+ Open the App integration tab.

  ![Cognito](/images/4.cognito/012-testlogin.png)

+ Scroll down to the **App client list** section
+ Select app client **demo-cognito**
  ![Cognito](/images/4.cognito/013-testlogin.png)

+ Scroll down to the **Hosted UI** section
+ Click **View hosted UI**
  ![Cognito](/images/4.cognito/014-testlogin.png)
  The Cognito sign-up screen will be displayed. Since we don't have any account yet, let's try to sign up by clicking on **Sign up**.
  ![Cognito](/images/4.cognito/015-testlogin.png)

  After signing up, you will be redirected to the **Not found** error screen. 
  ![Cognito](/images/4.cognito/016-testlogin.png)

  This is because we haven't configured the ALB to redirect to Cognito. 
  We will do this in the next step.



