---
title: "Week 8 Worklog"
date: 2025-11-11
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference only. Please **do not copy it verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 8 Goals:

* Start implementing the actual project using AWS serverless services.
* Build a basic backend workflow using DynamoDB, Lambda, and API Gateway.
* Register a domain and configure DNS via Route 53 for API exposure.

---

### Tasks for This Week:

| Day | Tasks                                                                                                                                                             | Start Date   | Completion Date | Reference       |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | ---------------- | ---------------- |
| 2   | - Analyze project requirements <br>- Define backend workflow: API Gateway → Lambda → DynamoDB                                                                     | 27/10/2025   | 27/10/2025       |  |
| 3   | - Create DynamoDB Table <br>&emsp; + Define Partition Key <br>&emsp; + Insert sample items                                                                        | 28/10/2025   | 28/10/2025       | |
| 4   | - Register domain via Route 53 <br>&emsp; + Purchase domain <br>&emsp; + Create Public Hosted Zone <br>&emsp; + Add A/CNAME records for routing setup            | 29/10/2025   | 29/10/2025       ||
| 5   | - Write Lambda functions for API <br>&emsp; + Implement CRUD operations with DynamoDB SDK <br>&emsp; + Create IAM Role for Lambda                                | 30/10/2025   | 30/10/2025       | |
| 6   | - Create API Gateway & integrate with Lambda <br>&emsp; + Set up REST API <br>&emsp; + Add GET/POST methods <br>&emsp; + Deploy stage <br>&emsp; + Test endpoint | 31/10/2025   | 31/10/2025       |  |

---

### Week 8 Achievements:

* Successfully created the **DynamoDB Table** for the project:
  * Defined the Partition Key
  * Added sample data to test workflow
  * Verified functionality via Query/Scan

* Completed **Route 53 domain registration**, including:
  * Creating a Public Hosted Zone
  * Adding DNS records (A, CNAME)
  * Verifying DNS propagation

* Built and deployed an **AWS Lambda function**:
  * Implemented logic for GET/POST requests
  * Integrated DynamoDB SDK for read/write operations
  * Configured appropriate IAM Role permissions

* Set up **API Gateway**:
  * Created REST API with resources and methods
  * Integrated with Lambda using Lambda Proxy
  * Deployed the `dev` stage
  * Successfully tested API endpoint

* Completed full serverless workflow integration:
  **Client → API Gateway → Lambda → DynamoDB**

* Strengthened understanding of real-world serverless architecture and how services tie together to form a working backend.

* …

