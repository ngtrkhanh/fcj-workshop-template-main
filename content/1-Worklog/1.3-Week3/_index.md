---
title: "Week 3 Worklog"
date: "2025-09-09T19:53:52+07:00"
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---



### Week 3 Objectives:

* Connect and get acquainted with members of First Cloud Journey.
* Understand basic AWS services, how to use the console & CLI.

### Tasks to be carried out this week:
Week 3 sẽ tập trung vào RDS + Auto Scaling EC2 + CloudWatch, và Friday (T6) ghi rõ bạn tham gia sự kiện AWS/FCJ.

***

### Week 3 – Worklog (15–19/09/2025 pattern tiếp tục)

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ----- | ---------- | ---------------- | ------------------ |
| MON | - Database Essentials with Amazon RDS: learn core concepts (DB instance, engine types, storage, Multi‑AZ, backup, security group for DB).[1] <br>- Review common use cases of RDS for web applications. | 22/09/2025 | 22/09/2025 | https://www.youtube.com/watch?v=TQFwQAre0H4&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=59|
| TUE | - Hands-on: create an RDS database instance in the same VPC as the EC2 web server from Week 2.<br>- Configure security so that only the EC2 instance (or app subnet) can connect to the RDS instance. | 23/09/2025 | 23/09/2025 | https://www.youtube.com/watch?v=SlP-KdSs3IM&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=225 |
| WED | - Scaling Applications with EC2 Auto Scaling: learn the concepts of Launch Template/Configuration, Auto Scaling Group, scaling policies, health checks.[3] <br>- Design a simple scaling policy based on CPU utilization for the web tier. | 24/09/2025 | 24/09/2025 |https://www.youtube.com/watch?v=hFVYG8WqfU0&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=80 |
| THU | - Hands-on: create an Auto Scaling Group for web EC2 instances across at least two AZs (if available).<br>- Test scale‑out/scale‑in behavior by adjusting thresholds or generating load. | 25/09/2025 | 25/09/2025 | https://000006.awsstudygroup.com[3] |
| FRI | - Attend an AWS event | 26/09/2025 | 26/09/2025 |
### Week 3 Achievements:

* Understood what AWS is and mastered the basic service groups: 
  * Compute
  * Storage
  * Networking 
  * Database
  * ...

* Successfully created and configured an AWS Free Tier account.

* Became familiar with the AWS Management Console and learned how to find, access, and use services via the web interface.

* Installed and configured AWS CLI on the computer, including:
  * Access Key
  * Secret Key
  * Default Region
  * ...

* Used AWS CLI to perform basic operations such as:

  * Check account & configuration information
  * Retrieve the list of regions
  * View EC2 service
  * Create and manage key pairs
  * Check information about running services
  * ...

* Acquired the ability to connect between the web interface and CLI to manage AWS resources in parallel.
* ...
