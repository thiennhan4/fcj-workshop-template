---
title: "Proposal"
date: 08-07-2026
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# Sports Facility Booking System

## AWS Web Application Deployment Solution

### 1. Executive Summary

The Sports Facility Booking System is designed to help users search for sports facilities, make online reservations, and manage their booking history through a web-based platform. The system is deployed on AWS using a Multi-tier Architecture to ensure high availability, security, and scalability.

The architecture uses Amazon ECS to deploy the application as containers, Amazon RDS as the relational database, Redis for caching, Amazon S3 for storing static files and images, CloudFront for fast content delivery, and Route 53 for domain name management. The system is protected by AWS WAF, while AWS Certificate Manager provides SSL certificates.

---

## 2. Problem Statement

### Current Challenges

Many sports facilities still manage reservations through phone calls or paper records, which leads to:

- Difficult reservation management.
- Booking conflicts.
- Lack of centralized payment and management systems.
- Limited scalability as the number of facilities increases.
- Reduced availability during periods of high traffic.

### Proposed Solution

Deploy the system on AWS using a cloud-native architecture.

Users access the website through Route 53 and CloudFront.

CloudFront works together with AWS WAF to accelerate content delivery and protect against web attacks.

An Application Load Balancer distributes incoming requests to containers running on Amazon ECS.

The application accesses an Amazon RDS database deployed in a Private Subnet.

Redis is used to cache frequently accessed data, reducing database workload.

Images and static assets are stored in Amazon S3.

Amazon ECR stores Docker images for the application.

AWS Secrets Manager securely stores database credentials and application secrets.

Amazon CloudWatch monitors the entire system and sends alerts through Amazon SNS.

### Benefits

- Automatic system scaling.
- High security.
- High availability.
- Simplified deployment of new versions.
- Reduced operational overhead.
- Improved performance through CloudFront and Redis.

---

## 3. Solution Architecture

The system is deployed within an Amazon VPC consisting of Public Subnets and Private Subnets across two Availability Zones to ensure high availability.

The workflow of the system is as follows:

1. Users access the website through Route 53.

2. CloudFront delivers content with lower latency.

3. AWS WAF inspects and filters malicious requests.

4. Valid requests are forwarded to the Application Load Balancer.

5. The ALB distributes traffic to containers running on Amazon ECS.

6. Amazon ECS processes business logic.

7. Data is stored in Amazon RDS (Primary Database).

8. Redis caches frequently accessed data.

9. Amazon RDS Standby in the second Availability Zone provides automatic failover and disaster recovery.

10. Amazon S3 stores frontend files and user-uploaded content.

11. Docker images are stored in Amazon ECR.

12. AWS Secrets Manager manages database credentials securely.

13. Amazon CloudWatch monitors all system resources.

14. Amazon SNS sends email notifications to administrators when issues occur.

![System Architecture](/images/diagram_aws.jpg)

### AWS Services Used

- Amazon Route 53
- Amazon CloudFront
- AWS WAF
- AWS Certificate Manager
- Amazon S3
- Amazon VPC
- Public Subnet
- Private Subnet
- NAT Gateway
- Application Load Balancer
- Amazon ECS
- Amazon RDS
- Amazon ElastiCache for Redis
- Amazon ECR
- AWS Secrets Manager
- Amazon CloudWatch
- Amazon SNS

### Architecture Components

**Edge Layer**

- Route 53 manages the domain name.
- CloudFront delivers content globally.
- AWS WAF protects the web application.
- AWS Certificate Manager provides SSL certificates.
- Amazon S3 stores the frontend and uploaded files.

**Application Layer**

- Application Load Balancer distributes incoming traffic.
- Amazon ECS runs the backend application.
- Amazon ECR stores Docker images.

**Database Layer**

- Amazon RDS Primary Database.
- Amazon RDS Standby Database.
- Redis Cache.

**Monitoring Layer**

- Amazon CloudWatch monitors system resources.
- Amazon SNS sends email alerts.

---

## 4. Technical Implementation

### Phase 1

- Analyze system requirements.
- Design the database.
- Design the AWS architecture.

### Phase 2

- Create the VPC.
- Configure subnets.
- Set up the NAT Gateway.
- Configure Security Groups.

### Phase 3

- Deploy Amazon ECS.
- Push Docker images to Amazon ECR.
- Configure the Application Load Balancer.

### Phase 4

- Deploy Amazon RDS.
- Configure Redis.
- Configure AWS Secrets Manager.

### Phase 5

- Configure CloudFront.
- Configure Route 53.
- Configure AWS WAF.
- Configure AWS Certificate Manager.

### Phase 6

- Set up Amazon CloudWatch.
- Configure Amazon SNS.
- Perform system testing.
- Deploy the system to production.

---

## 5. Implementation Roadmap

| Phase | Activities |
|--------|------------|
| Month 1 | System design |
| Month 2 | Backend and database development |
| Month 3 | ECS and RDS deployment |
| Month 4 | Testing and production deployment |

---

## 6. Budget Estimation

The estimated costs include:

- Amazon ECS
- Amazon RDS
- Amazon ElastiCache
- Amazon CloudFront
- Amazon Route 53
- Amazon S3
- NAT Gateway
- Application Load Balancer
- Amazon CloudWatch
- Amazon SNS

The total cost depends on the ECS/EC2 configuration, database size, and actual traffic volume.

---

## 7. Risk Assessment

### Risks

- Amazon ECS service failures.
- Database overload.
- Redis failures.
- DDoS attacks.
- Database storage exhaustion.

### Mitigation Strategies

- Deploy Amazon ECS across multiple Availability Zones.
- Enable Amazon RDS Multi-AZ deployment.
- Use CloudFront to reduce backend workload.
- Protect the application with AWS WAF.
- Monitor the system using CloudWatch and send alerts through Amazon SNS.

---

## 8. Expected Outcomes

- Stable 24/7 system availability.
- Scalability to support increasing numbers of users.
- Strong security.
- Faster deployment through Docker and Amazon ECS.
- High data availability with Amazon RDS Multi-AZ.
- Easy maintenance and future upgrades.
```
