---
title: "Translated Blogs"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

This section will list and introduce the blogs you have translated. For example:

###  [Blog 1 - Introducing Open Source Skills for AWS SDK Best Practices](3.1-Blog1/)
This blog introduces the AWS SDK Skills, part of the open-source AWS Agent Toolkit, designed to help AI coding agents use AWS SDKs correctly. It highlights common mistakes AI agents make — generating code that doesn't compile, skipping Paginators/Waiters (hurting performance), or catching overly generic exceptions (causing hard-to-detect logic bugs). Each Skill consists of a SKILL.md, a references/ folder, and scripts/, and is evaluated through real-world tasks involving S3, DynamoDB, and more. Three skills currently exist for Swift, JavaScript v3, and Python (Boto3), installable via the npx skills add command.

###  [Blog 2 - Securing .NET Microservices on AWS with Microsoft Entra ID](3.2-Blog2/)
This blog covers a security approach for communication between .NET microservices on AWS by combining Microsoft Entra ID (Azure AD) with the OAuth 2.0 Client Credentials Flow. Each service is registered as its own Application (with a Client ID, Client Secret, and Scope); to call another service, it must request an Access Token from Entra ID and pass it via the Authorization: Bearer header. The article emphasizes best practices such as storing Client Secrets in AWS Secrets Manager, caching Access Tokens for performance, using [Authorize] in ASP.NET Core, and evaluates the solution against the five pillars of the AWS Well-Architected Framework.

###  [Blog 3 - Improving App Performance with CDN Caching in AWS Amplify Hosting](3.3-Blog3/)
This blog discusses CDN caching improvements in AWS Amplify Hosting that boost site speed without requiring code changes. The key improvement is excluding cookies (tracking, session, etc.) from the Cache Key to raise the Cache Hit Ratio. Other enhancements include dedicated cache policies per content type (static/SSR/image), forwarding additional CloudFront headers, support for Next.js i18n via the Accept-Language header, and automatic Brotli compression. Benchmarks on Next.js 14 showed roughly a 98% improvement in response times and a 99.99% Cache Hit Ratio for static assets.