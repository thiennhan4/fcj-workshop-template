---
title: "Workshop"
date: 08-07-2026
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is provided for reference purposes only. Please **do not copy it directly** into your report, including this warning message.
{{% /notice %}}

# Deploying AWS Infrastructure for the SportBooking System

#### Overview

In this chapter, I deploy the cloud infrastructure for the **SportBooking** system on **Amazon Web Services (AWS)**. The entire infrastructure is provisioned using the **Infrastructure as Code (IaC)** approach with **Terraform**, enabling automated resource provisioning while ensuring consistency, scalability, and easier infrastructure management.

During the deployment process, I first prepare the development environment, then configure the network infrastructure, deploy the required AWS services, verify the status of each service, test the application after deployment, and configure security policies to ensure the system operates securely and reliably in the AWS Cloud environment.

The AWS services used in this project include:

+ **Amazon VPC** – Provides an isolated virtual network for the system, including Public Subnets, Private Subnets, Internet Gateway, NAT Gateway, Route Tables, and Security Groups.
+ **Amazon EC2** – Provides virtual machines for system administration and deployment testing.
+ **Amazon Elastic Container Registry (Amazon ECR)** – Stores Docker images before they are deployed to Amazon ECS.
+ **Amazon Elastic Container Service (Amazon ECS)** – Deploys and manages Docker containers running the SportBooking application.
+ **Amazon RDS PostgreSQL** – Provides a managed relational database service for application data.
+ **Amazon ElastiCache for Redis** – Delivers an in-memory caching solution to improve application performance.
+ **Amazon S3** – Stores application images, documents, and other uploaded files.
+ **AWS Secrets Manager** – Securely stores and manages sensitive information such as database credentials and application secrets.
+ **Application Load Balancer (ALB)** – Distributes incoming traffic across multiple application instances to improve availability and reliability.
+ **Amazon CloudWatch** – Monitors AWS resources, collects logs, and tracks application performance.
+ **Amazon SNS** – Sends notifications and alerts based on system events and monitoring metrics.

After completing this chapter, the entire **SportBooking** infrastructure and application are successfully deployed on AWS Cloud and are ready for testing and operation. Finally, all AWS resources are removed to prevent unnecessary charges after the deployment process. The estimated cost of running the infrastructure during testing ranges from approximately **USD 100 to USD 200**, depending on the duration of resource usage.

#### Contents

1. [Project Overview](5.1-Workshop-overview/)
2. [Preparation](5.2-Prerequiste/)
3. [Deploying AWS Network Infrastructure](5.3-vpc/)
4. [Deploying AWS Services](5.4-AWS-service-deployment/)
5. [Configuring Security Policies](5.5-Policy/)
6. [Cleanup Resources](5.6-Cleanup/)