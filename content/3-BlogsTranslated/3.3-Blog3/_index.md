---
title: "Blog 3"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---


# AWS Big Data Blog

## Cross-account data collaboration with Amazon DataZone and AWS analytics tools

Authors: Arun Pradeep Selvaraj, Piyush Mattoo, Mani Yamaraja — March 5, 2025  
Topics: Amazon DataZone, Amazon Redshift, AWS Glue, Technical How-to, Thought Leadership

Data sharing is critical to innovation, growth, and collaboration. Gartner notes that organizations promoting data sharing outperform peers on business value metrics. A simple access-and-share mechanism is essential, yet cross-account permissions and finding the right data across accounts are common challenges when publishing and consuming data products on AWS.

Amazon DataZone is a fully managed data management service to catalog, discover, share, and govern data across AWS.

---

## Solution overview

This solution enables cross-account collaboration using Amazon DataZone domain association while preserving security and governance. We publish data assets via the Amazon DataZone business data catalog so other accounts can discover them, then query those assets from another AWS account using tools such as Amazon Athena and the Amazon Redshift query editor.

- **Producer account**: hosts data assets and the Amazon DataZone domain.  
- **Consumer account**: needs access to producer data.  
- Domain association uses AWS Resource Access Manager (AWS RAM). If both accounts are in the same AWS Organizations organization, association is automatic; otherwise AWS RAM sends an invitation for the consumer to accept or decline.

Personas:
- **Data administrators**: own producer/consumer; create the domain, configure/accept domain associations.  
- **Data publishers**: in producer; create publish projects/environments, produce/publish assets, approve subscription requests.  
- **Data subscribers**: in consumer; create subscribe projects/environments, discover/subscribe to assets, query data for insights.

---

## Prerequisites

- Two AWS accounts: producer and consumer.  
- An Amazon Redshift provisioned cluster or Redshift Serverless workgroup in each account, provisioned by a data admin.  
- A secret in AWS Secrets Manager storing master user credentials for each Redshift cluster/workgroup. Data admins create secrets; publishers/subscribers obtain secret ARNs when creating environments/profiles.  
- Amazon DataZone uses Amazon Redshift datashares for cross-account sharing; both producer and consumer clusters must be encrypted and use supported RA3 types (ra3.16xlarge, ra3.4xlarge, ra3.xlplus) or Redshift Serverless. See datashare considerations for encryption.

High-level steps:
1) Create Amazon DataZone domain in producer.  
2) Send domain association request from producer to consumer.  
3) Accept domain association in consumer.  
4) Add data users to the domain.  
5) Create publish projects for AWS Glue and Amazon Redshift (producer).  
6) Create Glue and Redshift environments to publish assets (producer).  
7) Create and run data sources for Glue/Redshift to publish assets to the business catalog.  
8) Create subscribe projects for Glue/Redshift (consumer).  
9) Create environment profiles/environments for Glue/Redshift in subscribe projects.  
10) Subscribe to Glue/Redshift tables and consume via Athena and Redshift query editor.

---

## Create Amazon DataZone domain (producer)

- Log in to the producer console as data admin.  
- Create domain `Demo_cross_account_domain` (Quick setup enables default blueprints and environment profiles for data lake and data warehouse).

---

## Request domain association (producer → consumer)

- In the producer Amazon DataZone console, open the domain, go to **Associated Accounts**, enter consumer account ID(s), choose **Request association**.  
- Use policy `AWS RAM DataZonePortalReadWrite` so consumer users can call Amazon DataZone APIs and use the data portal.

---

## Accept domain association (consumer)

- Log in to consumer (same Region), open Amazon DataZone → **View requests** → select domain → **Review request** → **Accept association**.  
- Domain shows **associated**.  
- Enable environment blueprints: select domain → Blueprints → enable **DefaultDataLake** (provide Glue Manage Access role) and **DefaultDataWarehouse**.

---

## Add data users to the domain

- As data admin in producer: **User management** → **Add** → **Add IAM users**.  
- Add publisher IAM users from the current account; add subscriber IAM users from the associated consumer account.

---

## Create publish projects (producer)

- Data publisher in producer creates projects in the data portal:  
  - `Glue_Publish_Project` (AWS Glue assets)  
  - `Redshift_Publish_Project` (Amazon Redshift assets)

---

## Create publish environments (producer)

### Glue
- In `demo_cross_account_domain`, open `Glue_Publish_Project`, create environment `Glue_Publish_Environment` with default DataLakeProfile.  
- Leave producer_glue_db_name, consumer_glue_db_name, Workgroup_name blank.  
- Open Athena (Analytics tools), ensure `Glue_Publish_Environment` and database `glue_publish_environment_pub_db`.  
- Run CTAS to create sample table `mkt_sls_table` (sales/marketing sample). Verify the table exists.

### Redshift
- In `Redshift_Publish_Project`, create environment `Redshift_Publish_Environment` with default data warehouse profile.  
- Provide Redshift cluster/workgroup, database name, and secret ARN. Secrets must include tags:  
  - Cluster: `DataZone.rs.cluster: <cluster:db>`  
  - Serverless: `DataZone.rs.workgroup: <workgroup:db>`  
  - `AmazonDataZoneProject: <project_id>`  
  - `AmazonDataZoneDomain: <domain_id>`  
- In Redshift query editor, create table `rs_sls_tbl` via CTAS (sample sales data). Verify the table exists.

---

## Publish assets to the business data catalog (producer)

### Glue data source
- In `Glue_Publish_Project` → `Glue_Publish_Environment`, create data source `glue-publish-datasource`, type **AWS Glue**, select environment, database `glue_publish_environment_pub_db`, table selection `*`.  
- Run on demand; after run, `mkt_sls_table` appears. Review metadata → **Accept All** → **Publish Asset**.

### Redshift data source
- In `Redshift_Publish_Project` → `Redshift_Publish_Environment`, create data source `rs-publish-datasource`, type **Amazon Redshift**.  
- Provide cluster/workgroup and secret; select database `dev`, schema `datazone_env_redshift_publish_environment`.  
- Run on demand; after run, `rs_sls_tbl` appears. Review metadata → **Accept All** → **Publish Asset**.

---

## Create subscribe projects (consumer)

- In consumer data portal, create:  
  - `Glue_Subscribe_Project` (for AWS Glue assets)  
  - `Redshift_Subscribe_Project` (for Amazon Redshift assets)

---

## Create environment profiles and environments (consumer)

### Glue
- Create environment profile `glue_subscribe-env-profile`: Blueprint **Default Data Lake**; account = consumer; Authorized projects = All; Publishing = Publish from any database.  
- Create environment `glue_subscribe_environment` from the profile (optional: producer/consumer Glue DB names, workgroup). Wait until complete.

### Redshift
- In `Redshift_Subscribe_Project`, create profile `redshift_subscribe-env-profile`: Blueprint **Default Data Warehouse**; Parameter set = Enter my own; choose Cluster or Serverless; provide Redshift secret ARN; Authorized projects = All; Publishing = Publish any schema.  
- Create environment `redshift_subscribe_environment` from the profile.

---

## Subscribe to AWS Glue and Amazon Redshift tables

### Glue subscription
- As data subscriber (consumer), open `Glue_Subscribe_Project`, select **Market Sales Table** (`mkt_sls_table`) → **Subscribe** with justification.  
- Publisher approves; subscriber confirms in **Subscribed Assets**.  
- Open Amazon Athena (environment `glue_subscribe_environment`, DB `glue_subscribe_environment_sub_db`), preview `mkt_sls_table` and verify data.

### Redshift subscription
- In `Redshift_Subscribe_Project`, search **Sales Table** (`rs_sls_tbl`) → **Subscribe** with justification.  
- Publisher approves; subscriber confirms in **Subscribed Assets**.  
- Open Redshift Query Editor V2 via project link, create a connection with temporary IAM credentials, select DB for the environment, and run:  
  `SELECT * FROM "dev"."datazone_env_redshift_subscribe_environment"."rs_sls_tbl";`

---

## Cleanup

- Delete Amazon DataZone projects created for the walkthrough.  
- Delete the Amazon DataZone domain if it was created for the lab.  
- Delete Redshift clusters/workgroups and related Secrets Manager secrets in both producer and consumer accounts.

---

## Summary

Cross-account data sharing is complex due to permissions and security. This solution shows how to publish and consume data across AWS accounts using Amazon DataZone with AWS Glue and Amazon Redshift, maintaining consistent governance and secure access. You can monitor access/activity with AWS Lake Formation and CloudTrail (90-day default logs). Extend the pattern to more accounts as needed.

---

## About the authors

- **Arun Pradeep Selvaraj** – Senior Solutions Engineer at AWS; focuses on digital transformation and cloud modernization.  
- **Piyush Mattoo** – Senior Solutions Architect (Financial Services) at AWS; 10+ years building distributed, scalable systems; MS CS (UMass); enjoys camping/hiking.  
- **Mani Yamaraja** – Senior Customer Solutions Manager (Financial Services) at AWS; 10+ years guiding customer cloud journeys; customer-obsessed, designs tech aligned to business goals.
