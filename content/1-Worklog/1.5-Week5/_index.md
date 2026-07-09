---
title: "Week 5 Worklog"
date:  15-05-2026
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 5 Objectives:

* Study VPC Peering and its use cases.
* Study AWS Transit Gateway and compare with VPC Peering.
* Practice configuring VPC Peering and Transit Gateway labs.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Learn Module 03: VPC Peering <br>&emsp; + VPC Peering concepts and use cases <br>&emsp; + Cross-Region and Cross-Account peering <br>&emsp; + Limitations and routing considerations | 15/05/2026 | 15/05/2026      | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 3   | - **Practice:** Lab - Create VPC Peering Connection <br>&emsp; + Create VPC Peering between two VPCs in different Regions <br>&emsp; + Accept peering request and verify connectivity | 16/05/2026 | 16/05/2026      | <https://000019.awsstudygroup.com/> |
| 4   | - **Practice:** Lab - Configure Route Table for VPC Peering <br>&emsp; + Update Route Tables in both VPCs <br>&emsp; + Test cross-VPC communication between EC2 instances | 17/05/2026 | 17/05/2026      | <https://000019.awsstudygroup.com/> |
| 5   | - Learn Module 03: AWS Transit Gateway <br>&emsp; + Transit Gateway architecture and concepts <br>&emsp; + Comparison with traditional VPC Peering model <br>&emsp; + Hub-and-spoke network topology | 18/05/2026 | 18/05/2026      | <https://www.youtube.com/playlist?list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i> |
| 6   | - **Practice:** Lab - Create Transit Gateway & Attachments <br>&emsp; + Create Transit Gateway <br>&emsp; + Create Transit Gateway Attachments for multiple VPCs <br>&emsp; + Configure Transit Gateway Route Table | 19/05/2026 | 20/05/2026      | <https://000020.awsstudygroup.com/> |
| 7   | - **Practice:** Complete Transit Gateway Lab <br>&emsp; + Verify routing between attached VPCs <br>&emsp; + Test cross-VPC connectivity <br>&emsp; + Clean up resources | 21/05/2026 | 21/05/2026      | <https://000020.awsstudygroup.com/> |


### Week 5 Achievements:

* Understood VPC Peering concepts:
  * VPC Peering connection types (same Region, cross-Region, cross-Account)
  * Routing configuration for peered VPCs
  * Limitations: no transitive peering

* Successfully completed VPC Peering lab:
  * Created VPC Peering Connection between two VPCs in different Regions
  * Configured Route Tables and verified cross-VPC communication

* Understood AWS Transit Gateway architecture:
  * Hub-and-spoke topology for centralized network management
  * Advantages over traditional VPC Peering model
  * Transit Gateway Route Table concepts

* Successfully completed Transit Gateway lab:
  * Created Transit Gateway and attached multiple VPCs
  * Configured Transit Gateway Route Table
  * Verified routing between all attached VPCs
  * Cleaned up all resources after lab completion
