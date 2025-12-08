---
title: "Week 3 Worklog"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 3 Objectives:

* Learn Auto Scaling concepts and implementation.
* Configure Auto Scaling Groups for automatic instance management.
* Integrate Auto Scaling with Load Balancer for high availability.
* Understand and implement Elastic IP addresses.
* Set up SNS notifications for Auto Scaling events.
* Document AWS High Availability & Scaling concepts.

### Tasks to be carried out this week:
| Day | Task                                                                                                             | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| MON | - Learn Auto Scaling concepts: <br>&emsp; + Launch Templates <br>&emsp; + Auto Scaling Groups (ASG) <br>&emsp; + Scaling policies <br>&emsp; + Min/Max/Desired capacity <br>&emsp; + Health checks | 09/22/2025 | 09/22/2025 | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html> |
| TUE | - Create Launch Template for EC2 instances <br> - Configure Launch Template with AMI, instance type, security groups <br> - Configure user data scripts if needed <br> - Test Launch Template by launching instance | 09/23/2025 | 09/23/2025 | <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html> |
| WED | - Create Auto Scaling Group (ASG) <br> - Configure ASG with min/max/desired capacity <br> - Attach Launch Template to ASG <br> - Configure ASG to use multiple Availability Zones <br> - Integrate ASG with existing ALB Target Group | 09/24/2025 | 09/24/2025 | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/auto-scaling-groups.html> |
| THU | - Create CloudWatch alarms for CPU utilization <br> - Configure scale-out policy: Add instances when CPU > 50% <br> - Configure scale-in policy: Remove instances when CPU decreases <br> - Test scale-out by generating CPU load | 09/25/2025 | 09/25/2025 | <https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-simple-step.html> |
| FRI | - Test scale-in behavior when CPU load decreases <br> - Verify ASG integration with ALB for high availability <br> - Monitor Auto Scaling activities and instance lifecycle <br> - Learn about Elastic IP (EIP) concepts | 09/26/2025 | 09/26/2025 | <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html> |
| SAT | - Allocate Elastic IP address <br> - Assign EIP to EC2 instance for testing <br> - Create SNS topic for Auto Scaling notifications <br> - Configure ASG to send notifications to SNS topic | 09/27/2025 | 09/27/2025 | <https://docs.aws.amazon.com/sns/latest/dg/sns-getting-started.html> |
| SUN | - Write documentation explaining AWS High Availability & Scaling concepts <br> - Review and document Auto Scaling architecture <br> - Clean up test resources if needed | 09/28/2025 | 09/28/2025 | <> |


### Week 3 Achievements:

* Learned Auto Scaling concepts and implementation:
  * Launch Templates for standardized instance configuration
  * Auto Scaling Groups (ASG) for automatic instance management
  * Scaling policies and triggers
  * Min/Max/Desired capacity configuration
  * Health checks and instance replacement

* Successfully created Launch Template:
  * Configured Launch Template with AMI, instance type, and security groups
  * Set up user data scripts for instance initialization
  * Tested Launch Template by launching instances

* Configured Auto Scaling Group:
  * Created ASG with proper min/max/desired capacity settings
  * Attached Launch Template to ASG
  * Configured ASG across multiple Availability Zones
  * Integrated ASG with Application Load Balancer for high availability

* Implemented dynamic scaling:
  * Created CloudWatch alarms for CPU utilization monitoring
  * Configured scale-out policy to add instances when CPU usage > 50%
  * Configured scale-in policy to remove instances when CPU load decreases
  * Successfully tested both scale-out and scale-in behaviors

* Integrated with Load Balancer:
  * Connected ASG with existing ALB Target Group
  * Verified high availability through automatic instance distribution
  * Monitored Auto Scaling activities and instance lifecycle

* Implemented Elastic IP:
  * Learned Elastic IP concepts and use cases
  * Allocated Elastic IP address
  * Assigned EIP to EC2 instance for testing

* Set up notifications:
  * Created SNS topic for Auto Scaling notifications
  * Configured ASG to send scaling event notifications to SNS
  * Tested notification delivery for scaling activities

* Documented knowledge:
  * Wrote comprehensive documentation explaining AWS High Availability & Scaling concepts
  * Documented Auto Scaling architecture and best practices

* Gained hands-on experience with AWS Auto Scaling, high availability patterns, and infrastructure automation.
