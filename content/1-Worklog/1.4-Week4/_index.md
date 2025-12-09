---
title: "Week 4 Worklog"
date: "2025-09-09T19:53:52+07:00"
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---


### Week 4 Objectives:

* Connect and get acquainted with members of First Cloud Journey.
* Understand basic AWS services, how to use the console & CLI.

### Tasks to be carried out this week:
Dưới đây là **Week 4** (không có event), vẫn bám theo flow Cloud9 + S3 static website.

***

## Week 4 – Worklog
| Day | Task                                                                                                                                                                                                                                                                                          | Start Date | Completion Date | Reference Material                                                                                                                                                                                                                                                     |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MON | - Set up Hybrid DNS with Route 53 Resolver: learn basic concepts of Route 53, Route 53 Resolver, hybrid DNS between on‑prem and AWS, inbound/outbound endpoints, and Resolver rules (introduction).- Take notes about typical hybrid DNS use cases for enterprise environments.               | 06/10/2025 | 06/10/2025      | https://www.youtube.com/watch?v=FGicpWOmMDI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=46youtube​|
| TUE | - Follow the Hybrid DNS lab: create required VPCs, subnets and initial Route 53 configuration for the lab scenario.- Draw a small architecture diagram showing on‑prem DNS, Route 53 Resolver inbound/outbound endpoints, and VPCs.                                                           | 07/10/2025 | 07/10/2025      | https://000010.awsstudygroup.com/vi/|
| WED | - Configure Security Groups for the Hybrid DNS lab: keep only ICMP (ping) and RDP ports needed for testing, remove unused ports to follow least‑privilege and improve security.- Test connectivity (ping, RDP) to ensure Security Group rules work as expected.                               | 08/10/2025 | 08/10/2025      | https://www.youtube.com/watch?v=kE_krznNBFU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=49youtube|
| THU | - Complete Hybrid DNS with Route 53 Resolver: configure inbound and outbound Resolver endpoints and create Resolver rules to forward specific domains between on‑prem and AWS.- Test DNS resolution in both directions (from “on‑prem” to AWS and from AWS back to on‑prem).                  | 09/10/2025 | 09/10/2025      | https://www.youtube.com/watch?v=L-2YfZceoAU&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=61000003.awsstudygroup|
| FRI | - Set up AWS Transit Gateway: learn concepts and pricing (attachments, data processing) and create a Transit Gateway in the lab account.- Attach existing VPCs to the Transit Gateway and update VPC route tables so traffic between VPCs flows through the TGW; test cross‑VPC connectivity. | 10/10/2025 | 10/10/2025      | https://www.youtube.com/watch?v=W1m_OFPDui0&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i&index=68 https://www.youtube.com/watch?v=QSXgL2KodQI&list=PLahN4TLWtox2a3vElknwzU_urND8hLn1i|
### Week 4 Achievements:

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
