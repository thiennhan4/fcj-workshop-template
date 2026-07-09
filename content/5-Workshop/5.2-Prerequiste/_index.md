---
title : "Preparation Steps"
date : 08-07-2026
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

#### Development Environment Setup

Before deploying the SportBooking system to AWS Cloud, I prepared the development environment and installed the necessary tools for infrastructure provisioning, application deployment, and AWS resource management.

The tools used throughout the implementation include:

- Visual Studio Code
- Git
- Docker Desktop
- Terraform
- AWS CLI
- AWS Account

*Insert screenshots of the installed tools or development environment here.*

---

#### Configuring AWS CLI

After installing AWS CLI, I configured my AWS account so that Terraform and other tools could authenticate and interact with AWS services.

Run the following command:

```bash
aws configure
```

Then provide the following information:

- AWS Access Key ID
- AWS Secret Access Key
- Default Region
- Default Output Format

To verify that the configuration was successful, run:

```bash
aws sts get-caller-identity
```

This command confirms that AWS CLI has successfully connected to the AWS account and is ready for infrastructure deployment.

![aws_cli](/images/aws_cli.jpg)
![aws_cli_sts_get_caller_identity](/images/aws_cli_sts_get_caller_identity.jpg)

---

#### Preparing Terraform

To provision the infrastructure using the **Infrastructure as Code (IaC)** approach, I used Terraform to build the complete AWS architecture for the SportBooking system.

The Terraform configuration was organized into multiple files and modules to simplify management, scalability, and maintenance throughout the development process.

After completing the Terraform configuration files, I initialized the working directory by running:

```bash
terraform init
```

Next, I validated the configuration files:

```bash
terraform validate
```

Then I previewed the infrastructure deployment plan:

```bash
terraform plan
```

Once all configurations were validated successfully, I deployed the infrastructure using:

```bash
terraform apply
```

This process automatically provisions all AWS resources according to the designed architecture.

![terraform](/images/terraform.jpg)

---

#### Verifying Resources in the AWS Management Console

After Terraform successfully provisioned the infrastructure, I verified all resources in the AWS Management Console to ensure that the environment was created correctly and was ready for application deployment.

The resources inspected include:

- Amazon VPC
- Public Subnets and Private Subnets
- Internet Gateway and NAT Gateway
- Route Tables
- Security Groups
- Application Load Balancer
- Amazon ECS Cluster
- Amazon ECS Service
- Amazon ECR Repository
- Amazon RDS for PostgreSQL
- Amazon ElastiCache for Redis
- Amazon S3 Bucket
- AWS Secrets Manager
- Amazon CloudWatch
- Amazon SNS

This verification process confirms that all AWS resources have been provisioned according to the designed architecture and that the deployment environment is ready for deploying the SportBooking application to AWS Cloud.

![cloud](/images/ECS.jpg)
![cloud](/images/EC2.jpg)
![cloud](/images/ECR.jpg)