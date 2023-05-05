---
title : "Check result"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---
-  Enter the address **https://subdomain/demo-cognito/** in the browser.

    (Replace "subdomain" in the URL with your subdomain)

- Click **Go to dashboard**

    ![test](/images/5.test/001-index.png)

- You will be directed to the Cognito sign-in screen.

{{% notice info %}}
If you can access the dashboard screen without logging in, it may be because your browser is still caching. Please clear your cache and try again or use a private window to ensure accuracy.
{{% /notice %}}

- Enter the account information you previously registered and press Enter
![test](/images/5.test/002-login.png)
- After logging in, you will be redirected to the dashboard screen.
![test](/images/5.test/003-dashboard.png)
- From here, you can try logging out by clicking on **Logout**
- After logging out, you can still access the dashboard screen normally. This is because when we call the Cognito logout endpoint, only the Cognito session is deleted, while the ALB session is not. In the step of configuring the rule for the ALB, we set the session timeout to 180 seconds, so you can wait for 3 minutes after clicking the logout link, then try to access the dashboard screen again. Then, you will definitely have to log in again.

    You can see that:
- Before logging out, the browser has 2 cookies
![test](/images/5.test/004-beforelogout.png)
- After logging out, the browser still has 1 cookie for the ALB
![test](/images/5.test/005-afterlogout.png)
- To automatically delete the entire ALB session after logging out, we need to add additional backend processing. The goal of this lab exercise is to become familiar with how to create a simple website using ALB and Cognito to configure routing and authentication, so the backend processing will be addressed in another lab.

    Congratulations on completing the lab exercise. Remember to perform the resource clean up step to avoid unexpected costs.

    