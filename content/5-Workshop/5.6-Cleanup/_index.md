---
title : "Cleanup Resources"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

#### Cleanup Resources

After completing the deployment and testing of the **SportBooking** system, I proceeded to remove all AWS resources created during the implementation. Cleaning up unused resources helps prevent unnecessary AWS charges and ensures that the cloud environment remains organized for future deployments.

The resources were deleted in the appropriate order to avoid dependency conflicts between AWS services.

---

#### Cleanup

1. Delete the **Amazon ECS Service**.

+ Open the **Amazon ECS** console.
+ Select the SportBooking ECS Cluster.
+ Stop and delete the ECS Service.

![Cleanup ECS](/images/CleanUp/ECS.jpg)

---

2. Delete the **Amazon ECR Repository**.

+ Open the **Amazon ECR** console.
+ Remove all Docker images from the repository.
+ Delete the private repository after it is empty.

![Cleanup ECR](/images/CleanUp/ECR.jpg)

---

3. Delete the **Amazon EC2 Instance**.

+ Open the **Amazon EC2** console.
+ Select the EC2 instance created for the project.
+ Choose **Terminate Instance**.

![Cleanup EC2](/images/CleanUp/EC2.jpg)

---

4. Delete the **Amazon RDS Database**.

+ Open the **Amazon RDS** console.
+ Select the database instance.
+ Disable the **Final Snapshot** option if a backup is not required.
+ Confirm the database deletion.

![Cleanup RDS](/images/CleanUp/RDS.jpg)

---

5. Delete the **Amazon ElastiCache for Redis**.

+ Open the **Amazon ElastiCache** console.
+ Select the Redis cluster.
+ Delete the cache cluster.

![Cleanup ElastiCache](/images/CleanUp/ElastiCache.jpg)

---

6. Delete the **IAM Role**.

+ Open the **AWS IAM** console.
+ Select the IAM Role used by Amazon ECS.
+ Delete the role after all related resources have been removed.

![Cleanup IAM Role](/images/CleanUp/IAM_Role.jpg)

---

7. Delete the **Security Group**.

+ Open the **Amazon VPC** console.
+ Select the Security Group created for the project.
+ Delete the Security Group after confirming that no AWS resources are using it.

![Cleanup Security Group](/images/CleanUp/Security_Group.jpg)

---

8. Delete the **Subnets**.

+ Select the Public and Private Subnets created for the system.
+ Delete all subnets after removing their associated resources.

![Cleanup Subnet](/images/CleanUp/Subnet.jpg)

---

9. Delete the **Route Tables**.

+ Delete the Route Tables created for the project.
+ Ensure that they are no longer associated with any subnet before deletion.

![Cleanup Route Table](/images/CleanUp/Route_Table.jpg)

---

10. Delete the **Internet Gateway**.

+ Detach the Internet Gateway from the Amazon VPC.
+ Delete the Internet Gateway.

![Cleanup Internet Gateway](/images/CleanUp/VPC_InternetGateway.jpg)

---

11. Delete the **Amazon VPC**.

+ Open the **Amazon VPC** console.
+ Select the VPC created for the SportBooking system.
+ Delete the VPC after all associated resources have been removed.

![Cleanup VPC](/images/CleanUp/VPC.jpg)

---

#### Summary

After completing the cleanup process, all AWS resources associated with the **SportBooking** system were successfully removed. This cleanup process helps eliminate unnecessary AWS costs, maintains a clean cloud environment, and prepares the AWS account for future deployments.