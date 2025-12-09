---
title: "Week 9 Worklog"
date: 2025-11-18
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference only. Please **do not copy it verbatim** into your report, including this warning.
{{% /notice %}}

### Week 9 Goals:

* Integrate Google Authentication into Amazon Cognito (Google as an Identity Provider).
* Configure Amazon SES to send emails (notifications, verification, OTP).
* Test full flow: user login → Cognito authentication → SES email delivery.

---

### Tasks for This Week:

| Day | Tasks                                                                                                                                                          | Start | End | Reference |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ---- | ---------- |
| 2   | - Prepare Cognito environment <br> - Create new User Pool & App Client for Google Login                                                                        | 03/11/2025 | 03/11/2025 |  |
| 3   | - Configure Google OAuth: <br>&emsp; + Create OAuth Client ID in GCP <br>&emsp; + Retrieve Client ID & Secret                                                  | 04/11/2025 | 04/11/2025 | |
| 4   | - Integrate Google with Cognito: <br>&emsp; + Create Google Identity Provider <br>&emsp; + Attribute Mapping <br>&emsp; + Test login flow                      | 05/11/2025 | 05/11/2025 |  |
| 5   | - Set up Amazon SES: <br>&emsp; + Domain verification <br>&emsp; + Sender email verification <br>&emsp; + DKIM setup <br>&emsp; + Remove SES Sandbox limitation | 06/11/2025 | 06/11/2025 |  |
| 6   | - Build SES email Lambda <br>&emsp; + Integrate with API Gateway <br>&emsp; + Test sending email via REST API                                                  | 07/11/2025 | 07/11/2025 |  |

---

### Week 9 Achievements:

* Successfully integrated **Google Login with Amazon Cognito**:
  * Created User Pool & App Client
  * Set up Google OAuth in GCP
  * Added Google as an Identity Provider in Cognito
  * Verified login & token exchange workflow

* Fully configured **Amazon SES**:
  * Domain and email verification
  * DKIM enabled for improved email deliverability
  * SES successfully moved out of sandbox
  * Able to send verified emails

* Built a **Lambda function for email sending via SES**:
  * Supports OTP / verification / notification emails
  * Integrated with API Gateway for external triggering

* Verified entire authentication + email workflow:
  **Google Sign-in → Cognito Authentication → Lambda → SES Email Delivery**

* Improved understanding of OAuth provider integration & email service configuration within AWS.

* …
