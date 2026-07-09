---
title : "Verify Application Deployment"
date : 08-07-2026
weight : 4
chapter : false
pre : " <b> 5.4.4 </b> "
---

In this section, I verify the SportBooking application after the deployment process to ensure that the system is operating correctly on the AWS Cloud platform.

#### Verify API Endpoints

+ Access the application APIs through the Application Load Balancer (ALB).
+ Send requests to the system's API endpoints.
+ Verify that the application returns the expected responses.

![Application Load Balancer](/images/cloud/ALB/alb.jpg)

![API](/images/Api/test_api.jpg)

![API](/images/Api/test_api1.jpg)

![API](/images/Api/test_api2.jpg)

![API](/images/Api/test_api3.jpg)

![API](/images/Api/test_api4.jpg)

![API](/images/Api/test_api5.jpg)

![Swagger](/images/Api/swagger.jpg)

---

#### Verify Database Connectivity

+ Verify that the application can successfully connect to Amazon Aurora SQL Server / Amazon RDS.
+ Confirm that data can be retrieved from and stored in the database successfully.

![Amazon RDS](/images/cloud/RDS/RDS.jpg)

---

#### Verify Redis Connectivity

+ Verify that the application can successfully connect to Amazon ElastiCache for Redis.
+ Confirm that Redis operates correctly during application execution.

![Redis](/images/cloud/Redis/Redis.jpg)

![Amazon ElastiCache](/images/cloud/Redis/ElastiCache.jpg)

---

#### Verify AWS CLI Configuration

After configuring AWS CLI, I verified the configuration and authenticated the AWS account to ensure that the deployment environment was ready for use.

The verification included:

- AWS CLI version
- Configuration information (Access Key and Region)
- AWS account authentication
- Access permissions to AWS services

![AWS CLI](/images/aws_cli.jpg)

![AWS CLI - Get Caller Identity](/images/aws_cli_get_caller_identity.jpg)

---

#### Deployment Results

After completing the verification process, the SportBooking system was successfully deployed on AWS Cloud. All AWS services were operating normally, the application was accessible, database connectivity was functioning correctly, Redis was available, and the system successfully performed its core functionalities as designed.