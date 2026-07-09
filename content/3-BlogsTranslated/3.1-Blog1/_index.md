---
title: "Blog 1"
date: 08-07-2026
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Introducing Open Source Skills for AWS SDK Best Practices

We have released a collection of AWS SDK Skills as part of the open-source AWS Agent Toolkit. These AI-powered skills enable coding agents to follow AWS SDK best practices when generating code. The project is available on GitHub under the Apache 2.0 license.

---

## 1. The Problem

AI coding agents generally understand the overall structure of using AWS SDKs, but they often make mistakes in the implementation details. They may generate incorrect API names, use invalid parameter types, or overlook SDK-specific patterns such as paginators, waiters, and high-level APIs like the Amazon Simple Storage Service (Amazon S3) Transfer Manager.

These issues are especially common with newer SDKs, such as the AWS SDK for Swift, where AI agents frequently generate code that appears correct but fails to compile.

As developers increasingly rely on AI coding assistants to generate AWS SDK code, it is essential that these agents produce code that compiles successfully, follows AWS best practices, and uses each SDK as intended.

## 2. What Are Skills?

Skills are modular packages that provide AI coding agents with specialized knowledge about AWS SDKs. Each skill is developed by the SDK team responsible for a specific programming language and captures the common mistakes that AI agents frequently make when using that SDK.

A typical skill includes:

- **`SKILL.md`**
  - Contains the core guidance.
  - Provides SDK usage patterns.
  - Includes practical examples.

- **`references/`**
  - Contains in-depth reference documentation.
  - Loaded only when needed.

- **`scripts/`**
  - Contains scripts for automating:
    - Build
    - Test
    - Validation

Skills are independent of any particular coding agent and therefore work with any AI coding assistant that supports the **Open Skill Format**.

---

## 3. How Skills Prevent Common Errors

Skills are designed to help AI coding agents avoid common mistakes when working with AWS SDKs, including compilation errors, performance issues, and subtle runtime bugs.

### 3.1. Code That Fails to Compile

Compilation errors are among the most common problems when using newer SDKs because AI models may have outdated or limited training data.

For example, many AI agents generate the following code for the **AWS SDK for Swift**:

```swift
// What agents tend to write. Does not compile.
let client = S3Client()
let response = client.listBuckets(input: ListBucketsInput())
```

This code does not compile because:

- `S3Client()` is an `async throws` initializer.
- `listBuckets()` is also an `async throws` function.

After installing the Swift skill, the AI agent generates the correct implementation:

```swift
let config = try await S3Client.S3ClientConfig(region: "us-west-2")
let client = S3Client(config: config)
let response = try await client.listBuckets(input: ListBucketsInput())
```

As a result, the generated code compiles successfully and works as expected.

---

### 3.2. Code That Works but Performs Poorly

Some AI-generated code runs successfully but fails to take advantage of AWS SDK optimization features, such as:

- Using **Paginators** for APIs like `ListObjects`.
- Using **Waiters** to monitor resource status.
- Using high-level methods such as:
  - `upload_file`
  - `download_file`

Without these features, applications may:

- Retrieve only the first page of results.
- Make unnecessary API calls.
- Miss multipart upload capabilities.
- Perform poorly when handling large datasets.

When Skills are installed, AI agents automatically use the appropriate SDK features to improve both performance and cost efficiency.

---

### 3.3. Code That Contains Subtle Bugs

Some errors are difficult to detect, for example:

- Manually converting DynamoDB data types such as:

```json
{"S": "value"}
```

- Catching a generic `Exception` instead of a specific exception such as:

```text
ConditionalCheckFailedException
```

With Skills installed, AI agents will:

- Use the **Document Client** for automatic data conversion.
- Catch the correct exception types for each API.
- Significantly reduce subtle logic errors.

---

## 4. Measuring Effectiveness

Each Skill is evaluated using a benchmark suite containing real-world AWS SDK tasks, including:

- Amazon S3 operations.
- Amazon DynamoDB queries.
- Client configuration.
- Presigned URL generation.
- Credential management.

Generated code is evaluated based on whether it:

- Compiles successfully.
- Passes linting.
- Correctly completes the required task.

Each benchmark is executed twice:

1. Without Skills installed.
2. With the relevant Skill installed.

The results show that code generated with Skills consistently passes more tests and achieves higher overall quality.

---

## 5. Available Skills

| Skill | SDK | Coverage |
|-------|-----|----------|
| `aws-sdk-swift-usage` | AWS SDK for Swift | Async programming patterns, client configuration, client initialization |
| `aws-sdk-js-v3-usage` | AWS SDK for JavaScript v3 | Package structure, client architecture, middleware, runtime authentication |
| `aws-sdk-python-usage` | Boto3 / Botocore | Client vs. Resource APIs, Paginators, Waiters, exception handling |

---

## 6. Getting Started

To install a Skill from the **AWS Agent Toolkit**, run:

```bash
npx skills add aws/agent-toolkit-for-aws/skills --skill <skill>
```

Replace `<skill>` with the desired Skill name, for example:

- `aws-sdk-swift-usage`
- `aws-sdk-js-v3-usage`
- `aws-sdk-python-usage`

You can specify the `--skill` option multiple times to install multiple Skills simultaneously.

---

## 7. Key Takeaways

From this article, we can draw several important lessons:

- AI coding agents require specialized knowledge through **Skills** to use AWS SDKs correctly.
- Skills significantly reduce compilation errors, logic errors, and performance issues in AI-generated code.
- Leveraging SDK features such as **Paginators**, **Waiters**, and the **Document Client** helps generated code follow AWS best practices.
- Skills save developers time by reducing debugging efforts and improving code quality.

---

## 8. Applications

Skills can be applied in a variety of software development scenarios, including:

- Assisting AI coding agents in generating accurate AWS SDK code.
- Developing applications using Amazon S3, Amazon DynamoDB, and other AWS services.
- Helping new developers quickly learn AWS SDK usage.
- Increasing development productivity while reducing maintenance costs.
- Integrating with AI coding assistants such as Amazon Q Developer, GitHub Copilot, and other coding agents that support the Open Skill Format.

---

## 9. Conclusion

- Skills play a vital role in improving the quality of AI-generated code for AWS SDK development. By providing specialized guidance, practical examples, and best practices, Skills reduce compilation errors, improve runtime performance, and minimize subtle logic bugs.
- In addition, Skills enable AI agents to make proper use of AWS SDK features such as Paginators, Waiters, the Document Client, and high-level file transfer APIs, resulting in more reliable, efficient, and maintainable code.
- Overall, installing and using Skills is an essential step toward enabling AI coding agents to help developers build AWS applications faster, more accurately, and with significantly less manual debugging.