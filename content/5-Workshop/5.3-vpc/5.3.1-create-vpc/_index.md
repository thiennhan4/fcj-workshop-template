---
title : "Create Amazon VPC"
date : 08-07-2026
weight : 1
chapter : false
pre : " <b> 5.3.1 </b> "
---

1. Sign in to the **AWS Management Console** and open the **Amazon VPC** service.

2. In the left navigation pane, select **Your VPCs**, then click **Create VPC**.

![Create VPC](/images/cloud/VPC/Yours_VPCs.jpg)

---

3. In the **Create VPC** window, configure the following settings:

+ Select **VPC only** to create a new Virtual Private Cloud.
+ Enter a name for the VPC.
+ Configure an appropriate **IPv4 CIDR Block** based on the system architecture.
+ Keep the remaining settings as their default values.

---

4. After completing the configuration, click **Create VPC** to create the virtual network for the system.

AWS will automatically provision the VPC using the specified configuration.

![Create VPC](/images/cloud/VPC/Create_VPC.jpg)

---

5. After the VPC has been created successfully, verify it in the **Your VPCs** list.

Check the following information:

- VPC ID
- IPv4 CIDR Block
- State
- Default VPC
- Owner ID

This verification ensures that the VPC has been created successfully and is ready for the next configuration steps, including creating Subnets, Route Tables, Internet Gateway, and Security Groups.

![Your VPCs](/images/cloud/VPC/Overview_Subnet.jpg)

![Internet Gateway](/images/cloud/VPC/Internet_gateway.jpg)

![Route Table](/images/cloud/VPC/Route_Table.jpg)

![VPC Subnets](/images/cloud/VPC/VPC_Subnet.jpg)