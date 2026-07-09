---
title : "Create Public Subnet and Private Subnet"
date : 08-07-2026
weight : 2
chapter : false
pre : " <b> 5.3.2 </b> "
---

#### Create Public Subnet

1. Open the **Amazon VPC Console**.

2. In the left navigation pane, select **Subnets**, then click **Create subnet**.

*Insert the Subnets interface screenshot here.*

3. In the **Create subnet** window, configure the following:

+ Select the **VPC** created in the previous step.
+ Enter a name for the Public Subnet.
+ Select the appropriate **Availability Zone (AZ)**.
+ Configure the **IPv4 CIDR Block**.

Once completed, click **Create subnet** to create the Public Subnet.

![create VPC](/images/cloud/VPC/VPC_Subnet.jpg)

---

#### Create Private Subnet

1. Continue by clicking **Create subnet** to create the Private Subnet.

2. In the **Create subnet** window, configure the following:

+ Select the same **VPC** created earlier.
+ Enter a name for the Private Subnet.
+ Select the corresponding Availability Zone.
+ Configure an IPv4 CIDR Block different from the Public Subnet to avoid IP address overlap.

Once completed, click **Create subnet**.

![create VPC](/images/cloud/VPC/Yours_VPCs.jpg)

---

#### Verify the Subnets

After successful creation, return to the **Subnets** list to verify the resources just created.

Make sure the system has all of the following:

- Public Subnet 1
- Public Subnet 2
- Private Subnet 1
- Private Subnet 2

Also check the following information:

- Subnet ID
- Availability Zone
- IPv4 CIDR Block
- VPC
- State

![create VPC](/images/cloud/VPC/Overview_Subnet.jpg)
![create VPC](/images/cloud/VPC/Overview_YoursVPC.jpg)
---

#### Summary

After completing this step, the system has been fully configured with Public Subnets and Private Subnets in Amazon VPC.

The Public Subnets will be used to deploy resources that require internet connectivity, such as the Application Load Balancer and NAT Gateway. Meanwhile, the Private Subnets will be used to deploy Amazon ECS, Amazon RDS PostgreSQL, and Amazon ElastiCache Redis to enhance the system's security.

Separating Public Subnets and Private Subnets ensures that the SportBooking system's infrastructure architecture follows AWS best practices for security, scalability, and high availability.