---
title : "Introduce"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
In this lab, you will practice creating a simple website with authentication functions (registration, login, logout) using Application Load Balancer (ALB) and Amazon Cognito.
This website is in an EC2 instance behind ALB.
When user accesses the public page (which anyone can view), ALB will direct them straight to EC2.
If user accesses a private page (which can only be viewed by logged-in users), ALB will direct them to Cognito. After the user finishes logging in on Cognito, ALB will direct them to the requested resource on EC2.

#### Application Load Balancer (ALB)
ALB is a service provided by Amazon Web Services (AWS) that offers load balancing and traffic routing solutions for applications running on multiple servers.

#### Amazon Cognito
Amazon Cognito is a login and authentication management service for web and mobile applications. It enables developers to authenticate and authorize users through social Identity Providers (IdP) such as Facebook, Google, and Amazon, or through custom user accounts. Cognito provides user management, authorization, and activity tracking features, helping to reduce development effort and improve security for applications.
![ConnectPrivate](/images/arc-log.png) 