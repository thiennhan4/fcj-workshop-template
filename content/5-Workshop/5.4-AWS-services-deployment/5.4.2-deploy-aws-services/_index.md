---
title : "Deploy AWS Services"
date : 08-07-2026
weight : 2
chapter : false
pre : " <b> 5.4.2 </b> "
---

In this section, I deploy the AWS services required for the SportBooking system. These services are configured based on the designed architecture to support application deployment, data storage, container orchestration, and system monitoring.

1. Access the **AWS Management Console** and open the required AWS services.

2. Deploy **Amazon ECR (Elastic Container Registry)**.

+ Create a **Private Repository** to store the application's Docker images.
+ After the repository is created successfully, authenticate Docker with Amazon ECR and push the Docker image to the repository.

![Amazon ECR (Elastic Container Registry)](/images/cloud/ECR/ECR.jpg)

![Amazon ECR (Elastic Container Registry)](/images/cloud/ECR/Private_repo.jpg)

![Amazon ECR (Elastic Container Registry)](/images/cloud/ECR/success.jpg)

---

3. Deploy **Amazon ECS (Elastic Container Service)**.

+ Create an **Amazon ECS Cluster** to manage the application's containers.
+ Configure **Health Checks** to monitor the application status.
+ Create an **ECS Service** and associate it with the ECS Cluster to deploy the application.

![Amazon ECS - Clusters](/images/cloud/ECS/Clusters.jpg)

![Amazon ECS - Clusters](/images/cloud/ECS/test_Cluster.jpg)

![Amazon ECS - Health Check](/images/cloud/ECS/Health.jpg)

![Amazon ECS - Services](/images/cloud/ECS/Services.jpg)

![Amazon ECS - Services](/images/cloud/ECS/Services_succ.jpg)

---

4. Deploy **Amazon Aurora SQL Server / Amazon RDS**.

+ Create the SQL Server database.
+ Configure the database connection and Security Group.
+ Verify that the database has been created successfully.

![Amazon RDS](/images/cloud/RDS/RDS.jpg)

![Database](/images/cloud/RDS/Database.jpg)

---

5. Deploy **Amazon ElastiCache for Redis**.

+ Create a Redis OSS Cache.
+ Configure the cache cluster, VPC, Subnet Group, and Security Group.
+ Verify that the Redis cache is successfully deployed and reaches the **Available** status.

![ElastiCache](/images/cloud/ElastiCache/ElastiCache.jpg)

![ElastiCache](/images/cloud/ElastiCache/ElastiCache_success.jpg)

---

6. Deploy **Amazon S3**.

+ Create an Amazon S3 bucket to store images and application files.
+ Configure the appropriate access permissions for the bucket.

*Insert screenshots of the Amazon S3 deployment here.*

---

7. Deploy **Application Load Balancer (ALB)**.

+ Create a Target Group.
+ Create an Application Load Balancer.
+ Associate the Load Balancer with the Amazon ECS Service to distribute incoming traffic to the application containers.

![Application Load Balancer](/images/cloud/ALB/alb.jpg)

---

8. Deploy **Amazon EC2**.

+ Create an Amazon EC2 instance for system administration and testing purposes.
+ Configure the VPC, Subnet, and Security Group for the EC2 instance.
+ Verify that the EC2 instance is running successfully.

![Amazon EC2](/images/cloud/EC2/Overview.jpg)

![Load Balancer](/images/cloud/EC2/Load_Balances.jpg)

![Load Balancer](/images/cloud/EC2/Load_Balances1.jpg)

![Target Group](/images/cloud/EC2/Target_group)

![Amazon EC2](/images/cloud/EC2/EC2.jpg)

---

9. Deploy **AWS Secrets Manager**.

+ Create secrets to securely store sensitive application information.
+ Grant Amazon ECS permission to access the secrets through an IAM Role.

*Insert screenshots of AWS Secrets Manager here.*

---

After completing the above steps, all AWS services were successfully deployed and are ready to support the operation of the SportBooking system on AWS Cloud. The next section verifies the status of the deployed services and confirms that the deployment was completed successfully.