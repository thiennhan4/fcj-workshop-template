---
title: "Week 12 Worklog"
date: 03-07-2026
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 12 Objectives:

* Deploy the backend application and database on AWS services (EC2 and RDS).
* Configure S3 and CloudFront for sports field image storage and content delivery.
* Perform system testing (authentication, booking, payment, deployment).
* Complete final report and project handover.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Deploy backend core on Amazon EC2 <br>&emsp; + Configure EC2 security groups and launch instance <br>&emsp; + Pull code and run backend application on the server | 03/07/2026 | 03/07/2026      | <https://000004.awsstudygroup.com/> |
| 3   | - Set up Amazon RDS database service <br>&emsp; + Create PostgreSQL/MySQL database instance on RDS <br>&emsp; + Secure connection from EC2 backend to RDS database | 04/07/2026 | 04/07/2026      | <https://000005.awsstudygroup.com/> |
| 4   | - Configure Amazon S3 and CloudFront for static assets <br>&emsp; + Create S3 bucket for field images <br>&emsp; + Set up CloudFront distribution to cache and distribute images | 05/07/2026 | 05/07/2026      | <https://000057.awsstudygroup.com/> <br> <https://000094.awsstudygroup.com/> |
| 5   | - Perform unit and integration testing <br>&emsp; + Test registration, login, and authorization logic <br>&emsp; + Test booking placement, payment integration, and calendar updates | 06/07/2026 | 07/07/2026      | |
| 6   | - Test overall system deployment on AWS <br>&emsp; + Record deployment errors and optimize configurations | 08/07/2026 | 08/07/2026      | |
| 7   | - Finalize technical documentation and project source code <br> - Hand over source code, submit internship report, and summarize internship process | 09/07/2026 | 10/07/2026      | |


### Week 12 Achievements:

* Successfully deployed database and backend application on AWS:
  * Deployed database using Amazon RDS and successfully connected to the backend
  * Run backend service on Amazon EC2 instance within secure VPC security groups

* Set up cloud storage and content delivery network:
  * Uploaded and served sports field images via Amazon S3 bucket
  * Configured Amazon CloudFront to distribute image assets globally with low latency

* Completed comprehensive system testing:
  * Verified secure authentication flow and role-based permissions
  * Verified booking workflow, including calendar updates and payment callback integration
  * Identified and fixed network route configurations on AWS

* Handed over deliverables:
  * Completed the final internship report summarizing learnings and AWS architecture
  * Finalized code repository, technical docs, and successfully completed internship handover
