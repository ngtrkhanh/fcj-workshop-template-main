---
title: "Week 2 Worklog"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 2 Objectives:

* Learn advanced VPC architecture and networking concepts.
* Understand and implement public/private subnet configurations.
* Configure Internet Gateway and NAT Gateway for network connectivity.
* Deploy and manage EC2 instances in VPC subnets.
* Learn and implement Application Load Balancer (ALB) for load distribution.

### Tasks to be carried out this week:
| Day | Task                                                                                                             | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| MON | - Learn advanced VPC architecture: <br>&emsp; + CIDR blocks and subnetting <br>&emsp; + Public and private subnets <br>&emsp; + Route tables and routing <br>&emsp; + Internet Gateway (IGW) <br>&emsp; + NAT Gateway | 09/15/2025 | 09/15/2025 | <https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html> |
| TUE | - Create a new VPC with proper CIDR block <br> - Create 2 public subnets in different Availability Zones <br> - Create 2 private subnets in different Availability Zones <br> - Configure route tables for public and private subnets | 09/16/2025 | 09/16/2025 | <https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html> |
| WED | - Create and attach Internet Gateway to VPC <br> - Configure public route table to route traffic to Internet Gateway <br> - Create NAT Gateway in public subnet <br> - Configure private route table to route traffic to NAT Gateway | 09/17/2025 | 09/17/2025 | <https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html> <br><br> <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html> |
| THU | - Launch EC2 instance in public subnet <br> - Configure Security Groups for HTTP/HTTPS/SSH access <br> - Connect to EC2 instance via SSH <br> - Test network connectivity | 09/18/2025 | 09/18/2025 | <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html> |
| FRI | - Learn about Application Load Balancer (ALB) <br> - Create Target Group and configure health checks <br> - Create ALB and attach to Target Group <br> - Launch multiple EC2 instances and attach to Target Group | 09/19/2025 | 09/19/2025 | <https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html> |
| SAT | - Test load balancing functionality <br> - Verify traffic distribution across instances <br> - Test health check behavior | 09/20/2025 | 09/20/2025 | <> |
| SUN | - Review and document VPC architecture <br> - Clean up resources if needed | 09/21/2025 | 09/21/2025 | <> |


### Week 2 Achievements:

* Learned advanced VPC architecture concepts:
  * CIDR blocks and subnet design
  * Public and private subnet configurations
  * Route tables and routing mechanisms
  * Internet Gateway for public internet access
  * NAT Gateway for private subnet internet access

* Successfully created a new VPC with:
  * 2 public subnets in different Availability Zones
  * 2 private subnets in different Availability Zones
  * Proper CIDR block allocation and subnet design

* Configured networking infrastructure:
  * Created and attached Internet Gateway to VPC
  * Configured public route table to route traffic to Internet Gateway
  * Created NAT Gateway in public subnet
  * Configured private route table to route traffic through NAT Gateway

* Deployed and managed EC2 instances:
  * Launched EC2 instance in public subnet
  * Connected to EC2 instance via SSH successfully
  * Configured Security Groups for HTTP/HTTPS/SSH access
  * Tested network connectivity and access

* Implemented Application Load Balancer (ALB):
  * Learned ALB concepts and use cases
  * Created Target Group with health check configuration
  * Created Application Load Balancer
  * Attached multiple EC2 instances to Target Group
  * Tested load balancing and traffic distribution

* Gained hands-on experience with AWS networking services and advanced EC2 configurations.
