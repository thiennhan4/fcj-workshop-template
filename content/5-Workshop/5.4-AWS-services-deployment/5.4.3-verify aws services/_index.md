---
title : "Verify AWS Services"
date : 08-07-2026
weight : 3
chapter : false
pre : " <b> 5.4.3 </b> "
---

In this section, Members in group verify the operational status of the deployed AWS services to ensure that the entire infrastructure has been configured correctly and is ready to support the SportBooking system.

#### Verify Amazon EC2

+ Check the status of the Amazon EC2 instance.
+ Ensure that the EC2 instance is in the **Running** state.

![Amazon EC2](/images/cloud/EC2/EC2.jpg)

---

#### Verify Amazon ECR

+ Verify that the Docker image has been successfully pushed to the Private Repository.
+ Confirm that the repository is operating correctly.

![Amazon ECR (Elastic Container Registry)](/images/cloud/ECR/ECR.jpg)

---

#### Verify Amazon ECS

+ Check the status of the Amazon ECS Cluster.
+ Verify that the ECS Service is in the **Active** state.
+ Verify the application's **Health Status**.

![Amazon ECS - Clusters](/images/cloud/ECS/Clusters.jpg)

![Amazon ECS - Services](/images/cloud/ECS/Services.jpg)

![Amazon ECS - Health Status](/images/cloud/ECS/Health.jpg)

---

#### Verify Amazon Aurora SQL Server / Amazon RDS

+ Check the status of the database instance.
+ Ensure that the database is in the **Available** state.

![Amazon RDS](/images/cloud/RDS/RDS.jpg)

![Database](/images/cloud/RDS/Database.jpg)

---

#### Verify Amazon ElastiCache for Redis

+ Check the status of the Redis OSS cache.
+ Ensure that the cache is in the **Available** state.

![Amazon ElastiCache for Redis](/images/cloud/Redis/Redis.jpg)

---

#### Verify Application Load Balancer

+ Check the status of the Target Group.
+ Verify the health checks of the Application Load Balancer.
+ Ensure that all registered targets are in the **Healthy** state.

![Application Load Balancer](/images/cloud/ALB/alb.jpg)

---

#### Summary

After completing the verification process, all AWS services were operating successfully and were ready to support the deployment and operation of the SportBooking system on AWS Cloud.