---
title : "AWS Network Infrastructure Deployment"
date : 08-07-2026
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

#### Overview

In this section, I deploy the network infrastructure for the **SportBooking** system on Amazon Web Services (AWS). The objective is to build an isolated virtual network using **Amazon VPC** to ensure security, scalability, and provide the necessary networking foundation for deploying the system's AWS services.

The network infrastructure consists of **Amazon VPC**, **Public Subnets**, **Private Subnets**, **Internet Gateway**, **Security Groups**, **NAT Gateway**, and **Route Tables**. These components work together to create a secure and highly available network architecture. Resources that require Internet access are deployed within the Public Subnets, while backend services and databases are hosted in the Private Subnets to enhance security.

![VPC Architecture Diagram](/images/diagram_vpc.jpg)

#### Contents

- [Create Amazon VPC](3.1-create-vpc/)

![Amazon VPC](/images/cloud/VPC/Create_VPC.jpg)

- [Create Public and Private Subnets](3.2-create-subnets/)

![Amazon VPC](/images/cloud/VPC/Yours_VPCs.jpg)

![Amazon VPC Subnets](/images/cloud/VPC/VPC_Subnet.jpg)

- [Configure Internet Gateway, Security Groups, and Route Tables](3.3-network-configuration/)

![Internet Gateway](/images/cloud/VPC/Internet_gateway.jpg)

![Route Table](/images/cloud/VPC/Route_Table.jpg)

![Security Group](/images/cloud/VPC/security_group.jpg)