---
title : "Introduction"
date : 06/07/2026
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### SportBooking Project Overview

The **SportBooking** system is designed to provide a reliable, secure, and scalable online sports venue booking and management platform. The entire infrastructure is automatically provisioned on **AWS (Amazon Web Services)** using **Terraform** as the Infrastructure as Code (IaC) tool, ensuring consistency, repeatability, and simplified infrastructure management.

#### System Architecture Diagram

The following figure illustrates the overall cloud architecture of the SportBooking system deployed on AWS.

![AWS Architecture Overview](/images/diagram_aws.jpg)

#### Main Components of the Cloud Architecture

The system architecture is divided into three primary layers to optimize both performance and security.

1. **Edge Layer**
   * **Amazon Route 53 & AWS WAF:** Handle DNS routing and protect the application against common web attacks such as SQL Injection and DDoS.
   * **Amazon CloudFront:** Acts as a Content Delivery Network (CDN) to accelerate the delivery of static frontend assets stored in **Amazon S3 Frontend**.
   * **AWS Certificate Manager (ACM):** Manages and provisions SSL/TLS certificates to secure HTTPS communication.

2. **Network & Compute Layer**
   * **Amazon VPC (Virtual Private Cloud):** Provides an isolated network environment with separate **Public Subnets** (hosting the ALB and NAT Gateway) and **Private Subnets** (hosting the application services).
   * **AWS Fargate (Amazon ECS):** Runs the **.NET 9** backend application as Docker containers across two Availability Zones (Multi-AZ) to ensure high availability and fault tolerance.
   * **Application Load Balancer (ALB):** Receives incoming requests from CloudFront and distributes traffic across healthy ECS tasks.

3. **Data & Management Layer**
   * **Amazon RDS & Amazon ElastiCache (Redis):** Provide the primary relational database with a standby instance and an in-memory cache, both deployed inside isolated private data subnets.
   * **Amazon ECR & AWS Secrets Manager:** Store Docker container images securely and manage sensitive information such as database connection strings and application secrets.
   * **Monitoring Group (Amazon CloudWatch & Amazon SNS):** Monitor system health, collect metrics, and automatically send email notifications whenever issues are detected.

---

#### Deployment Process and System Verification

The project was successfully packaged, deployed, and verified through a standard manual CI/CD workflow.

* **Infrastructure Provisioning:** Configured the AWS profile and used **Terraform** to automatically provision 35 AWS cloud resources.
* **Build and Deployment:** The backend application developed with **.NET 9** was containerized using Docker, pushed to **Amazon ECR (Singapore Region)**, and deployed to an **Amazon ECS Fargate** cluster.
* **Health Check:** The **Application Load Balancer (ALB)** Target Group confirmed that all ECS services were healthy, and the application successfully responded to the `/health` endpoint with the status **OK**.

##### API Testing Results Using Postman

The core backend APIs were successfully tested against the cloud environment using real data.

1. **Authentication Features**
   * **User Registration (`POST /api/auth/register`):** Successfully creates a new user account and returns a valid JWT access token (`200 OK`).
   * **Data Validation:** Correctly handles duplicate username registration by returning the HTTP status code `409 Conflict` with the message *"Username already exists."*
   * **User Login (`POST /api/auth/login`):** Successfully authenticates users and grants authorized access.

2. **Business Functionality (`GET /api/venues`)**
   * Successfully retrieves the list of sports venues (for example, *Bach Khoa Sports Complex - Premium Football Field*) from the Amazon RDS database and returns the data in JSON format.

![overview](/images/test_api.jpg)