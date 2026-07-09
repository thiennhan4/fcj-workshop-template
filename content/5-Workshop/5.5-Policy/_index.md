---
title : "Configure Security Policies"
date : 08-07-2026
weight : 5
chapter : false
pre : " <b> 5.5 </b> "
---

#### Overview

In this section, I configure the security policies for the SportBooking system to control access between AWS services. Applying appropriate security policies ensures that only authorized resources can access system services, thereby enhancing security and minimizing operational risks.

---

#### Configure IAM Role for Amazon ECS

+ Create an IAM Role for Amazon ECS Tasks.
+ Grant the required permissions for the application to access Amazon ECR, Amazon CloudWatch, and AWS Secrets Manager.

![IAM Role](/images/cloud/IAM/IAM_Role.jpg)

---

#### Configure AWS Secrets Manager

+ Create a secret to securely store sensitive application information.
+ Grant Amazon ECS permission to access the secret through the IAM Role.



---

#### Configure Security Groups

+ Control network traffic between the Application Load Balancer, Amazon ECS, Amazon RDS, and Amazon ElastiCache.
+ Allow only the required inbound and outbound ports for each service.

![Security Group](/images/cloud/VPC/security_group.jpg)

---

#### Verify Security Policies

+ Verify that the IAM Role has been successfully assigned to Amazon ECS.
+ Verify that the application can access secrets stored in AWS Secrets Manager.
+ Verify that the configured Security Groups are functioning as expected.

*Insert screenshots of the security policy verification here.*

---

#### Summary

After completing the configuration, the SportBooking system was secured using appropriate AWS security policies. Access to AWS services was restricted according to the assigned permissions, ensuring a secure environment for deploying and operating the application on AWS Cloud.