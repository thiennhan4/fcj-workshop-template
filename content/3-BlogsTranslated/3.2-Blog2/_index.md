---
title: "Blog 2"
date: 08-07-2026
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---


# SECURING .NET MICROSERVICES ON AWS WITH MICROSOFT ENTRA ID

While learning about Microservices architecture on AWS, I came across the article **"Securing .NET Microservices with Entra ID on AWS"** published on the AWS .NET Blog. What impressed me most is how AWS combines **Microsoft Entra ID (formerly Azure AD)** with **OAuth 2.0 Client Credentials Flow** to build a secure authentication and authorization mechanism between .NET microservices running on AWS.

---

## 1. The Challenge

In a Microservices architecture, services frequently communicate with each other. For example:

- Order Service calls Inventory Service to check product availability.
- Inventory Service then calls Pricing Service to calculate product pricing.

Without a proper authentication mechanism, services may access one another without sufficient control, increasing the risk of unauthorized access and data exposure.

---

## 2. AWS Solution

AWS recommends registering each microservice as an **Application** in Microsoft Entra ID. Each service is assigned its own:

- Client ID
- Client Secret
- Scope (permissions)

When **Service A** needs to communicate with **Service B**, the process is as follows:

1. Service A sends its Client ID and Client Secret to Microsoft Entra ID.
2. Entra ID validates the credentials and issues an **Access Token**.
3. Service A sends a request to Service B with the Access Token in the `Authorization: Bearer` header.
4. Service B validates the Access Token before processing the request.

This ensures that only authorized services can access protected APIs.

---

## 3. Key Highlights

The article also introduces several best practices for securing service-to-service communication:

- Use **OAuth 2.0 Client Credentials Flow** for machine-to-machine authentication.
- Store **Client Secrets** securely in **AWS Secrets Manager** instead of hard-coding them.
- Cache **Access Tokens** until they are close to expiration to reduce authentication requests and improve performance.
- Use the `[Authorize]` attribute in ASP.NET Core to automatically protect APIs from unauthorized requests.

---

## 4. Evaluation Based on the AWS Well-Architected Framework

### Security

- Each microservice has its own identity and permissions.
- Only authorized services are allowed to access protected APIs.

### Operational Excellence

- Secrets are centrally managed using AWS Secrets Manager.
- Credentials can be rotated and managed more efficiently.

### Reliability

- Access Tokens are validated and refreshed when necessary.
- Authentication remains stable and reliable across services.

### Performance Efficiency

- Token caching reduces latency.
- Fewer authentication requests are sent to Microsoft Entra ID.

### Cost Optimization

- Reduces unnecessary authentication requests.
- Takes advantage of AWS managed services to lower operational costs.

---

## 5. Conclusion

In my opinion, this is an effective solution for organizations running **.NET Microservices** on AWS while using **Microsoft Entra ID** as their identity provider. By implementing **OAuth 2.0 Client Credentials Flow**, each microservice has its own identity and communicates securely with other services. Combined with AWS Secrets Manager and token caching, this approach improves security, scalability, and operational efficiency while following AWS security best practices.

---

## 6. Original Article

https://aws.amazon.com/blogs/dotnet/securing-net-microservices-with-entra-id-on-aws/

---

## 7. Guide

- Read the original AWS article to understand the complete architecture.
- Learn more about OAuth 2.0 Client Credentials Flow and Microsoft Entra ID.
- Practice implementing secure service-to-service authentication for .NET Microservices on Amazon ECS, Amazon EKS, or AWS Fargate using AWS Secrets Manager.