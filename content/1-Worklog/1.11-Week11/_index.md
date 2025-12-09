---
title: "Week 11 Worklog"
date: 2025-12-02
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The content below is for reference only. Please **do not copy it verbatim** into your report.
{{% /notice %}}

### Week 11 Goals:

* Integrate frontend with backend using **AWS Amplify**.  
* Use **Cognito** for authentication (login, JWT, API Key) in frontend.  
* Integrate Lambda + Resend + API Gateway into frontend via Amplify API.  
* Deploy full CI/CD automatically via **Amplify Console**.

---

### Tasks for This Week:

| Day | Tasks                                                                                                                                                                       | Start       | End         | Reference |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | ----------- | ---------- |
| 2   | - Configure Amplify project <br>&emsp; + `amplify init` <br>&emsp; + Connect frontend (React/Vue/Angular) <br>&emsp; + Add Amplify Auth (Cognito User Pool)                  | 17/11/2025  | 17/11/2025  | AWS Amplify Docs |
| 3   | - Integrate Lambda + Resend API via **Amplify API** <br>&emsp; + Create REST/GraphQL endpoint <br>&emsp; + Configure authentication using Cognito JWT/API Key               | 18/11/2025  | 18/11/2025  | Amplify Docs, Cognito Docs |
| 4   | - Test frontend → Amplify API → Lambda → Resend <br>&emsp; + Verify Cognito login works <br>&emsp; + Send OTP/notification emails from frontend                              | 19/11/2025  | 19/11/2025  | Project Docs |
| 5   | - Deploy CI/CD via **Amplify Console** <br>&emsp; + Connect GitHub/GitLab/CodeCommit repo <br>&emsp; + Auto build & deploy frontend + backend Lambda                         | 20/11/2025  | 20/11/2025  | Amplify Console Docs |
| 6   | - Test end-to-end pipeline <br>&emsp; + Push code → Amplify auto deploy <br>&emsp; + Check frontend UI, API authentication, and email sending via Resend                     | 21/11/2025  | 21/11/2025  | CloudWatch Logs |

---

### Week 11 Achievements:

* Fully integrated **frontend with backend via Amplify**:
  * Call Lambda + Resend API from frontend
  * Cognito authentication (login, JWT, API Key) works
  * OTP/verification/notification emails sent successfully

* Deployed **fully automated CI/CD via Amplify Console**:
  * Repo as source (GitHub/GitLab/CodeCommit)
  * Auto build & deploy frontend + backend
  * Production updated automatically on push

* End-to-end workflow tested:
  **Frontend → Cognito Auth → Amplify API → Lambda → Resend → Email → Frontend displays notification**

* Learned how to integrate **serverless full-stack with Amplify + Cognito + Lambda + Resend** and CI/CD automation.

* …
