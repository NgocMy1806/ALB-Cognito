---
title : "Create website in EC2"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 2.6</b> "
---

1. Access the newly created EC2

    This lab will use EC2 instance connect to access EC2.
+ Tick the instance that was just created.
+ Click **Connect**.
![EC2](/images/2.prerequisite/014-ec2connect.png)
![EC2](/images/2.prerequisite/015-ec2connect.png)

2. Install Apache web server on EC2

    To ensure that all your software packages are up to date, run the following command:
    ```
    sudo yum update -y
    ```
    ![EC2](/images/2.prerequisite/017-yumpdate.png)

    Run the following command to install Apache:
    ```
    sudo yum install -y httpd
    ```
    ![EC2](/images/2.prerequisite/018-installhttpd.png)

    Start Apache:
    ```
    sudo systemctl start httpd
    ```

    Use the systemctl command to configure the Apache web server to start every time the system starts.
    ```
    sudo systemctl enable httpd
    ```

    You can verify that httpd is enabled by running the following command:
    ```
    sudo systemctl is-enabled httpd

    ```
    ![EC2](/images/2.prerequisite/019-starthttpd.png)

3. Create a website on EC2

      Next, we will create a simple website with 3 pages,the index page and the logged out page are public pages that everyone can access, and the dashboard page is a private page that only logged-in users can see.

    Here are the detailed steps to create the website:
  + Navigate to the **/var/www/html** directory with command `cd /var/www/html`.
  + Create a folder named **demo-cognito** with command `sudo mkdir demo-cognito`.
  + Navigate to the **demo-cognito** directory with command `cd demo-cognito`.
![EC2](/images/2.prerequisite/020-mkdir.png)
  + Create the index.html file with command `sudo nano index.html`.Enter the following content for the index file:
    ```
    <html>
      <body>
        <h1>Welcome to the demo-cognito website</h1>
        <p>This is the index page</p>
        <a href="dashboard.html">Go to dashboard</a>
      </body>
    </html>
    ```
     ![EC2](/images/2.prerequisite/021-index.png)
  Save the file content by pressing the Ctrl+X key combination, then press Y and Enter.

  + Create the dashboard.html file with command  `sudo nano dashboard.html`.Enter the following content for the dasboard file:
    ```
    <html>
      <body>
        <h1>Congratulations!</h1>
        <p>You are logged in. This is dashboard page</p>
        <a href="logged_out.html">Logout</a>
      </body>
    </html>
    ```
    ![EC2](/images/2.prerequisite/022-dashboard.png)
  Save the file content by pressing the Ctrl+X key combination, then press Y and Enter.

  + Create the logged_out.html file with command  `sudo nano logged_out.html`.Enter the following content for the logged_out file:
    ```
    <html>
      <body>
        <h1>You are logged out</h1>
        <p>Goodbye!</p>
        <a href="index.html">Return to home page</a>
      </body>
    </html>
    ```
    ![EC2](/images/2.prerequisite/023-logged_out.png)
  Save the file content by pressing the Ctrl+X key combination, then press Y and Enter.

  + After creating all the files, restart the Apache web server with command  `sudo service httpd restart`.
  ![EC2](/images/2.prerequisite/024-restarthttpd.png)


    Now, you have successfully created a simple website on EC2.


