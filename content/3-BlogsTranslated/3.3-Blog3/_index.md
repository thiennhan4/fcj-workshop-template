---
title: "Blog 3"
date: 08-07-2026
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---


# IMPROVING APPLICATION PERFORMANCE WITH CDN CACHING IN AWS AMPLIFY HOSTING

While learning about **AWS Amplify Hosting**, I came across the article **"CDN Caching Improvements for Better App Performance with AWS Amplify Hosting"** published on the AWS Front-End Web & Mobile Blog. What impressed me most is how AWS optimized the CDN caching mechanism to improve website performance without requiring developers to make significant changes to their applications.

These improvements focus on increasing the **Cache Hit Ratio**, reducing unnecessary requests to the origin server, and taking full advantage of the **Amazon CloudFront Global Edge Network**. As a result, applications can deliver content faster while reducing server workload and operational costs.

---

## 1. The Challenge

Modern web applications, especially those built with React, Next.js, or other static site frameworks, rely heavily on Content Delivery Networks (CDNs) to provide fast user experiences.

When a user visits a website, Amazon CloudFront first checks whether the requested content already exists in its cache.

- If the content is cached (**Cache Hit**), it is immediately served from the nearest Edge Location.
- If the content is not cached (**Cache Miss**), CloudFront forwards the request to the origin server, retrieves the content, and stores it for future requests.

However, many applications suffer from low cache efficiency because their cache keys include unnecessary information, especially **Cookies**.

For example:

- Google Analytics cookies
- Session cookies
- Tracking cookies

Since every user has different cookie values, CloudFront treats each request as unique even when requesting the exact same page.

This results in:

- Lower Cache Hit Ratio
- More requests reaching the origin server
- Higher latency
- Reduced application performance

---

## 2. AWS Solution

To solve these issues, AWS introduced several caching improvements for Amplify Hosting.

### Optimized Cache Policies

Amplify Hosting now applies different cache policies for different content types, including:

- Static Content
- Server-Side Rendered (SSR) Content
- Image Optimization Content

Each content type has its own cache duration (TTL) and cache key configuration, allowing CloudFront to cache resources more efficiently.

---

### Removing Cookies from the Cache Key

One of the most significant improvements is the ability to remove cookies from the cache key.

For example:

```
https://example.com

Cookie:
ga-session-id=123456
```

Previously, every different cookie value generated a unique cache key.

By excluding unnecessary cookies from the cache key, multiple users can share the same cached content instead of generating separate cache entries.

This leads to:

- Higher Cache Hit Ratio
- Fewer origin requests
- Faster response times
- Better overall performance

---

### Additional CloudFront Headers

Amplify Hosting now forwards additional CloudFront headers such as:

- User-Agent
- Referer
- CloudFront-Viewer-Country
- CloudFront-Viewer-City

These headers allow developers to:

- Personalize content
- Detect user locations
- Analyze client devices
- Implement more advanced server-side logic

---

### Native Next.js Internationalization (i18n)

Amplify Hosting now supports **Next.js Internationalization (i18n)** natively.

By forwarding the **Accept-Language** header, Next.js applications can automatically detect a user's preferred language directly from the browser request and display localized content without additional configuration.

---

### Brotli Compression

AWS also enables **Brotli Compression** by default for all Amplify Hosting applications.

Compared to traditional compression methods, Brotli produces smaller files, resulting in:

- Faster page loading
- Reduced bandwidth usage
- Better SEO performance
- Improved experience for mobile users

---

## 3. Performance Results

AWS benchmarked these improvements using a **Next.js 14** application.

The results showed:

- Approximately **98%** improvement in average response time.
- Approximately **98%** improvement in p95 response time.
- Up to **99.99% Cache Hit Ratio** for static assets.

In addition, the official AWS Amplify documentation website consistently achieved a cache hit ratio above **90%**, demonstrating the effectiveness of these caching optimizations in real-world environments.

---

## 4. Evaluation Based on the AWS Well-Architected Framework

### Performance Efficiency

Optimized cache policies allow CloudFront to serve content directly from nearby Edge Locations, significantly reducing latency and improving response times.

### Cost Optimization

A higher Cache Hit Ratio reduces the number of requests sent to the origin server, lowering compute and bandwidth costs.

### Reliability

CloudFront distributes content across its global edge network and automatically invalidates cache after deployments, ensuring users always receive updated content.

### Operational Excellence

Developers can configure cache settings directly through the AWS Amplify Console, AWS CLI, or APIs, making cache management simpler and more consistent.

---

## 5. Conclusion

In my opinion, this is one of the most valuable performance improvements introduced to AWS Amplify Hosting. By optimizing cache policies, removing unnecessary cookies from the cache key, enabling Brotli compression, and supporting additional CloudFront features, AWS significantly improves website performance without requiring major application changes.

For developers deploying React, Next.js, or static websites on Amplify Hosting, these enhancements provide an easy way to increase loading speed, improve user experience, and reduce infrastructure costs.

---

## 6. Original Article

https://aws.amazon.com/blogs/mobile/cdn-caching-improvements-for-better-app-performance-with-aws-amplify-hosting/

---

## 7. Guide

- Learn how Amazon CloudFront handles CDN caching.
- Deploy a React or Next.js application on AWS Amplify Hosting.
- Compare the Cache Hit Ratio before and after removing cookies from the cache key.
- Experiment with the new cache policies to evaluate their impact on application performance.