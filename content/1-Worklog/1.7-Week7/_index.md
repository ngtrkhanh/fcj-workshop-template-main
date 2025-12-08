---
title: "Week 7 Worklog"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 7 Objectives:

* Learn serverless concepts with AWS Lambda.
* Create and test a simple Lambda function.
* Expose Lambda through API Gateway.
* Test the API using tools like Postman.

### Tasks to be carried out this week:
| Day | Task                                                                                                             | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| MON | - Learn serverless and AWS Lambda basics: when to use Lambda, pricing, and limitations | 10/20/2025 | 10/20/2025 | <https://docs.aws.amazon.com/lambda/latest/dg/welcome.html> |
| TUE | - Create a simple Lambda function (Hello World / JSON response) <br> - Test the function in the AWS Console | 10/21/2025 | 10/21/2025 | <> |
| WED | - Configure environment variables and basic IAM role for Lambda execution | 10/22/2025 | 10/22/2025 | <https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html> |
| THU | - Create an API Gateway (HTTP/REST) and integrate it with the Lambda function | 10/23/2025 | 10/23/2025 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html> |
| FRI | - Deploy API to a stage and obtain the invoke URL <br> - Test the API using Postman (check methods, status codes, payload) | 10/24/2025 | 10/24/2025 | <> |
| SAT | - Review CloudWatch Logs for the Lambda function <br> - Troubleshoot any errors from API calls | 10/25/2025 | 10/25/2025 | <> |
| SUN | - Document the Lambda + API Gateway architecture and main configuration steps | 10/26/2025 | 10/26/2025 | <> |


### Week 7 Achievements:

* Learned core AWS Lambda concepts:
  * Event-driven compute
  * Stateless execution model
  * Function handler and runtime configuration

* Created a simple Lambda function that returns a JSON response and tested it directly from the AWS Console.

* Integrated Lambda with API Gateway:
  * Created an API (HTTP/REST) and configured methods to invoke the Lambda function
  * Deployed the API to a stage and obtained the invoke URL

* Tested the API endpoint using Postman:
  * Sent HTTP requests and validated status codes and response payloads
  * Verified that Lambda was invoked correctly via CloudWatch Logs
