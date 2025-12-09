---
title: "Week 10 Worklog"
date: 2025-11-25
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---


### Week 10 Goals:

* Find an alternative email solution after SES sandbox removal request was rejected.  
* Switch to **Resend** as the primary email delivery service.  
* Configure **API authentication** (API Key / JWT) to protect the email endpoint.  
* Rebuild the email workflow using Resend.

---

### Tasks for This Week:

| Day | Tasks                                                                                                                                                      | Start       | End         | Reference |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | ----------- | ---------- |
| 2   | - Received SES sandbox removal rejection <br> - Evaluate project email requirements and possible alternatives                                              | 10/11/2025  | 10/11/2025  | |
| 3   | - Research Resend: <br>&emsp; + Generate API Key <br>&emsp; + Domain verification <br>&emsp; + Explore email API usage                                   | 11/11/2025  | 11/11/2025  | https://resend.com/docs |
| 4   | - Integrate Resend with Lambda: <br>&emsp; + Use SDK/HTTP API <br>&emsp; + Create email templates <br>&emsp; + Test email sending                        | 12/11/2025  | 12/11/2025  |  |
| 5   | - Configure API Authentication: <br>&emsp; + API Key or <br>&emsp; + JWT via Cognito <br>&emsp; + Enable auth in API Gateway                              | 13/11/2025  | 13/11/2025  |  |
| 6   | - End-to-End Testing: <br>&emsp; + Client → API Gateway → Lambda → Resend <br>&emsp; + Validate tokens <br>&emsp; + Debug logs in CloudWatch             | 14/11/2025  | 14/11/2025  | CloudWatch Logs |

---

### Week 10 Achievements:

* **SES sandbox removal request was rejected**, causing limitations:
  * Unable to send emails to unverified addresses
  * Not suitable for production usage
  * Required switching to an external provider

* Successfully migrated to **Resend**:
  * Created API Key
  * Verified domain for better deliverability
  * Sent emails successfully using Resend API

* Integrated **Lambda + Resend**:
  * Supports HTML templates
  * Email types: OTP, verification, notification
  * (Optional) Stored API Key securely in AWS Secrets Manager

* Implemented **API Authentication**:
  * API Key or JWT Cognito authentication
  * API Gateway now requires authentication to trigger Lambda
  * Improved security of email API endpoint

* Completed full workflow testing:
  **Client → Authenticated API Gateway → Lambda → Resend → Email Delivered**

* Strengthened understanding of external email providers and API authentication methods.

* …
