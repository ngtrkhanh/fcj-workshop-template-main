---
title: "Week 4 Worklog"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 4 Objectives:

* Learn managed database concepts with Amazon RDS.
* Create and configure an RDS MySQL instance.
* Connect an EC2 instance securely to RDS.
* Understand and test RDS backup and snapshot features.

### Tasks to be carried out this week:
| Day | Task                                                                                                             | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| MON | - Learn Amazon RDS concepts: <br>&emsp; + What is RDS? <br>&emsp; + Supported engines (MySQL, PostgreSQL, etc.) <br>&emsp; + RDS vs self-managed database on EC2 <br>&emsp; + Single-AZ vs Multi-AZ | 09/29/2025 | 09/29/2025 | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html> |
| TUE | - Review networking requirements for RDS: <br>&emsp; + DB subnet groups <br>&emsp; + Security Groups for RDS and EC2 <br>&emsp; + VPC considerations | 09/30/2025 | 09/30/2025 | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.html> |
| WED | - Create an RDS MySQL instance: <br>&emsp; + Choose instance class and storage <br>&emsp; + Configure initial database settings <br>&emsp; + Set backup window and retention | 10/01/2025 | 10/01/2025 | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_CreateDBInstance.html> |
| THU | - Configure Security Groups and networking so EC2 can connect to RDS <br> - Test connectivity from EC2 to RDS using MySQL client <br> - Run simple CRUD queries | 10/02/2025 | 10/02/2025 | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html> |
| FRI | - Explore RDS backup features: <br>&emsp; + Automated backups <br>&emsp; + Manual snapshots <br>&emsp; + Point-in-time recovery overview | 10/03/2025 | 10/03/2025 | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithAutomatedBackups.html> |
| SAT | - Create and restore from a manual snapshot for testing <br> - Validate that restored instance works correctly | 10/04/2025 | 10/04/2025 | <> |
| SUN | - Document the RDS architecture, connectivity from EC2, and backup/restore procedures | 10/05/2025 | 10/05/2025 | <> |


### Week 4 Achievements:

* Created an Amazon RDS MySQL instance with appropriate instance class, storage, and security configuration.

* Configured Security Groups and networking so that an EC2 instance could securely connect to the RDS endpoint.

* Successfully connected from EC2 to RDS using MySQL client tools and tested basic CRUD operations.

* Explored and tested RDS backup features:
  * Automated backups and backup retention
  * Manual snapshots
  * Restoring an instance from a snapshot for recovery testing

* Documented key RDS concepts such as:
  * Single-AZ vs Multi-AZ deployments
  * Storage options and performance considerations
  * Connectivity patterns between application tiers and RDS
