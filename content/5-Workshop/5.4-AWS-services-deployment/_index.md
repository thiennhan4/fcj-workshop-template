---
title : "Deploying AWS Services"
date : 08-07-2026
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

#### Overview

In this section, I proceed to deploy the AWS services for the **SportBooking** system based on the infrastructure architecture built in the previous section. The goal of this step is to deploy the compute, storage, database, and monitoring services to ensure the system can operate stably on the AWS Cloud platform.

The services deployed include:

- Amazon EC2
- Amazon Elastic Container Registry (Amazon ECR)
- Amazon Elastic Container Service (Amazon ECS)
- Amazon Aurora PostgreSQL / Amazon RDS
- Amazon ElastiCache for Redis
- Amazon S3
- AWS Secrets Manager
- Application Load Balancer (ALB)
- Amazon CloudWatch
...

Combining the above services helps build a modern, scalable architecture that increases availability while ensuring security and performance for the SportBooking system during operation.

![Architecture Overview](/images/diagram_aws.jpg)

#### Contents

- [Prepare Resources](4.1-prepare-resources/)
- [Deploy AWS Services](4.2-deploy-aws-services/)
- [Verify AWS Services](4.3-verify-aws-services/)
- [Validate Application Deployment](4.4-validate-application-deployment/)