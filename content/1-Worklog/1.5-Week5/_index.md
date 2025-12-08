---
title: "Week 5 Worklog"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 5 Objectives:

* Learn object storage concepts with Amazon S3.
* Practice uploading, organizing, and securing data in S3 buckets.
* Enable and test S3 versioning.
* Create and test a basic CloudFront distribution in front of S3.

### Tasks to be carried out this week:
| Day | Task                                                                                                             | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| MON | - Learn Amazon S3 basics: buckets, objects, folders, regions, and pricing model | 10/06/2025 | 10/06/2025 | <https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html> |
| TUE | - Create an S3 bucket and practice uploading/downloading objects <br> - Organize data using folders/prefixes | 10/07/2025 | 10/07/2025 | <> |
| WED | - Configure S3 permissions: <br>&emsp; + Bucket policies vs object ACLs <br>&emsp; + Test private vs public access | 10/08/2025 | 10/08/2025 | <https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html> |
| THU | - Enable versioning on the S3 bucket <br> - Upload multiple versions of a file and test restoring previous versions | 10/09/2025 | 10/09/2025 | <https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html> |
| FRI | - Create a basic CloudFront distribution using the S3 bucket as origin <br> - Configure default behavior and cache settings | 10/10/2025 | 10/10/2025 | <https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html> |
| SAT | - Test CloudFront access via the distribution domain <br> - Observe caching and invalidation behavior | 10/11/2025 | 10/11/2025 | <> |
| SUN | - Document S3 and CloudFront usage, security considerations, and typical use cases | 10/12/2025 | 10/12/2025 | <> |


### Week 5 Achievements:

* Worked with Amazon S3 by creating buckets, organizing data into folders, and uploading various objects.

* Configured basic S3 permissions and tested different access levels (private/public, pre-signed URLs if applicable).

* Enabled S3 bucket versioning and verified the ability to recover or roll back to previous object versions.

* Created a CloudFront distribution using an S3 bucket as the origin and:
  * Tested content delivery via the CloudFront domain name
  * Observed caching behavior and propagation delay

* Documented key concepts for S3 and CloudFront:
  * Differences between S3 and traditional file storage
  * Basic security and permission models for S3
  * How CloudFront improves latency and offloads traffic from S3
