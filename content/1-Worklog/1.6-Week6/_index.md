---
title: "Week 6 Worklog"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 6 Objectives:

* Learn IAM concepts: users, roles, groups, and policies.
* Configure basic permissions following least-privilege principles.
* Enable and test MFA for increased account security.
* Explore CloudTrail logging for auditing API activity.

### Tasks to be carried out this week:
| Day | Task                                                                                                             | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| MON | - Learn IAM basics: users, groups, roles, policies <br> - Review IAM best practices (root account, MFA, least privilege) | 10/13/2025 | 10/13/2025 | <https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html> |
| TUE | - Create IAM users and groups <br> - Attach managed policies for specific tasks (e.g., read-only, S3 access)    | 10/14/2025 | 10/14/2025 | <> |
| WED | - Write or inspect simple JSON IAM policies <br> - Test allowed/denied actions by logging in as IAM users       | 10/15/2025 | 10/15/2025 | <https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html> |
| THU | - Enable MFA for root and/or important IAM users <br> - Test login with MFA enabled and note recovery options   | 10/16/2025 | 10/16/2025 | <https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html> |
| FRI | - Enable AWS CloudTrail in the account <br> - View and filter basic events (login, IAM, EC2, S3 operations)     | 10/17/2025 | 10/17/2025 | <https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html> |
| SAT | - Review and adjust IAM permissions based on CloudTrail and least-privilege principles                           | 10/18/2025 | 10/18/2025 | <> |
| SUN | - Document IAM structure, key policies, MFA configuration, and CloudTrail usage                                  | 10/19/2025 | 10/19/2025 | <> |


### Week 6 Achievements:

* Learned IAM fundamentals:
  * IAM users, groups, roles
  * Managed and inline policies
  * Policy JSON structure and evaluation logic (Allow, Deny, Effect, Action, Resource)

* Configured basic IAM permissions:
  * Created IAM users with limited, task-focused permissions
  * Attached policies following least-privilege principles
  * Verified access by logging in as the IAM user and testing allowed/denied actions

* Enabled Multi-Factor Authentication (MFA) for critical accounts (root and/or IAM users) and:
  * Tested login flows with MFA enabled
  * Documented backup and recovery considerations for MFA devices

* Enabled AWS CloudTrail and:
  * Viewed account activity logs for key actions (login, IAM, EC2, S3…)
  * Understood how CloudTrail supports auditing and security investigations
