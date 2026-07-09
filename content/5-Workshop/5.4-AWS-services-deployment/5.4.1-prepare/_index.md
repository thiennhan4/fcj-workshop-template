---
title : "Prepare Resources"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.4.1 </b> "
---

#### Overview

Before deploying the SportBooking system to the AWS Cloud platform, I prepared the required resources and verified the deployment environment to ensure that the deployment process could be performed smoothly and successfully.

The resources prepared include:

- Amazon EC2
- Amazon ECR (Private Repository)
- Amazon ECS
- Amazon Aurora PostgreSQL / Amazon RDS
- Amazon ElastiCache for Redis
- Amazon S3
- AWS Secrets Manager
- Application Load Balancer
- Amazon CloudWatch

![Architecture Overview](/images/diagram_aws.jpg)

---

#### Prepare the Application Source Code

Before deployment, I reviewed the entire SportBooking source code to ensure that the application functioned correctly in the development environment.

The project consists of the following components:

- Backend API
- Frontend
- Dockerfile
- Terraform
- Environment configuration file (.env)

![Project Structure](/images/layout.jpg)

---

#### Prepare the Docker Image

The application is packaged as a Docker image to simplify deployment on Amazon ECS.

The preparation process includes:

- Reviewing the Dockerfile.
- Building the Docker image.
- Verifying that the Docker image was built successfully.

![Docker](/images/docker/docker_file.jpg)

![Docker](/images/docker/docker_file1.jpg)

![Docker](/images/docker/docker_file_yml.jpg)

![Docker](/images/docker/docker_file_yml_1.jpg)

![Docker](/images/docker/docker_file_yml_2.jpg)

---

#### Prepare the Terraform Configuration

Before provisioning the infrastructure, I reviewed the Terraform configuration files to ensure that all required AWS resources were properly defined.

The resources managed by Terraform include:

- Network infrastructure
- Compute services
- Database services
- Cache services
- Storage services
- Monitoring services

![Terraform](/images/terraform.jpg)

---

#### Verify the AWS Environment

Finally, I verified the AWS environment before starting the deployment process.

The verification included:

- AWS Account
- AWS CLI
- IAM Permissions
- AWS Region
- Terraform connectivity with AWS

These verification steps ensure that Terraform has the necessary permissions to provision and manage AWS resources successfully.

![AWS CLI](/images/aws_cli.jpg)

![AWS CLI - Get Caller Identity](/images/aws_cli_sts_get_caller_identity.jpg)

---

#### Summary

After completing the preparation phase, the application source code, Docker image, Terraform configuration, and AWS environment were fully prepared for deployment. In the following section, I will deploy the AWS services and configure the cloud infrastructure according to the designed system architecture.