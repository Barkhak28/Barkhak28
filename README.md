# Cloud Computing & Business Insights: CloudCatalyst Portfolio

![Cloud Foundation Badge](images/cloud_foundation_badge.png)

_Cloud Computing Foundation_ certification badge earned by **Barkha Kukreja**, demonstrating fundamental cloud expertise. This portfolio project leverages those cloud skills to deliver business insights from real-world data. The project showcases an AWS-powered data analytics pipeline developed to derive insights from the City of Vancouver’s business licence dataset.

---

## Objective

This project aimed to develop an end-to-end **Data Analytic Platform (DAP)** on AWS to analyze **City of Vancouver business license data (2013–2024)** and uncover meaningful business insights. This involved designing a robust cloud-based data pipeline to ingest and process a large public dataset, ensure data quality and security, and enable interactive analysis. By accomplishing this, the project demonstrates how cloud services can transform open data into valuable insights into urban business activity, supporting data-driven decision-making for stakeholders (e.g., city officials, entrepreneurs, or potential investors).

---

## Dataset

**City of Vancouver Business Licences (2013–2024)**, a public open dataset containing detailed records of business licences issued in the City of Vancouver from 2013 up to May 5, 2024. [City of Vancouver Open Data Portal](https://opendata.vancouver.ca/explore/dataset/business-licences-2013-to-2024/)

### Key Attributes

- **Licence Details:** Licence number, status (e.g. issued, expired, or gone out of business), issue date and expiry date (business licences are typically annual).
- **Business Information:** Business name and trade name, business type category (original classification), number of employees, and fee paid for the licence.
- **Location Information:** Business address and geographic coordinates (if the business is within city limits).

In total, the dataset contains over 780,000 records, reflecting the city’s active business landscape over 11+ years. (Under Licence By-law No. 4450, every business in Vancouver must obtain a valid licence to operate).

> **Note:** In May 2024, the City streamlined its business licence categories, consolidating 500+ business types into fewer than 100. This project’s analysis uses the original categories for consistency across 2013–2024 data. (Records from 2013–early 2024 use the pre-consolidation categories, as provided in the open dataset.) Data quality considerations from the source were also noted. For example, addresses for home-based businesses are partially redacted for privacy, and a unique ID (Licence RSN) is used to identify each licence to avoid any duplication issues.

### Dataset Visualization

**Figure 1**: A graph for business licensing activity patterns and yearly contributions from business authorization fees in White Rock city from 2013–2024.

![Business Licensing Graph](images/figure_28_part1.png)

*Note:* Displays annual issued licence counts and total fees, highlighting economic fluctuations and growth trends over the study period.

---

## Methodology

To achieve the project objectives, a full AWS-based data pipeline was implemented with the following steps:

### Data Ingestion

The raw data (downloaded as CSV from Vancouver’s Open Data Portal) was **ingested into Amazon S3**, establishing a data lake for raw and processed data. An **AWS KMS** (Key Management Service) key was used to encrypt the data at rest in S3 for security. Versioning was enabled on the S3 bucket to track any changes to the dataset over time.

![Encryption Settings for Raw Data Bucket](images/figure_32_part2.png)

*Note:* Demonstrates secure storage of raw dataset using AWS KMS-managed keys.

### Data Preparation & Cleaning

Using **AWS Glue DataBrew**, the dataset was profiled and cleaned through a no-code/low-code interface. This involved handling missing or anonymized fields, standardizing date and string formats, and filtering out irrelevant or duplicate records. A **DataBrew recipe** was created to document all transformation steps. This recipe was then applied in a DataBrew job, which output a **cleansed, enriched dataset** back to S3 in parquet format.

![AWS Glue DataBrew Cleaning Recipe Configuration](images/figure_35_part1.png)

*Note:* Highlights visual transformation steps applied to prepare clean, queryable data.

### Data Cataloging

An **AWS Glue Data Catalog** database and table were set up to catalog the cleaned data. The schema was defined so that other services could easily query the data. This was done by running an AWS Glue Crawler on the cleaned data in S3.

### Data Analysis (Interactive Queries)

**Amazon Athena** analyzed the data directly from S3 via SQL queries:
- *Time-series analysis*: Counting new licences issued per year and total fees collected.
- *Category analysis*: Identifying most common business categories.
- *Status analysis*: Examining licence status trends.
- *Geographic analysis*: Summarizing licences by neighbourhood.

![Athena SQL Query for Aggregating Licence Data by Year](images/figure_30_part2.png)

*Note:* Illustrates the SQL used to derive key annual business metrics using Amazon Athena.

### Monitoring & Logging

**AWS CloudWatch** and **AWS CloudTrail** monitored the platform’s operations. CloudWatch Logs captured execution details and metrics. CloudTrail provided an audit trail for actions taken on AWS resources.

![AWS CloudWatch Dashboard for Project Metrics](images/figure_44_part2.png)

*Note:* Displays usage metrics and query performance logs for data pipeline visibility.

---

## Tools & Technologies

- **Amazon S3:** Scalable object storage used as the data lake.

  ![System-Level Analytical Output in Parquet Format](images/figure_28_part2.png)

  *Note:* Demonstrates how data is efficiently stored in parquet format for querying.

- **AWS Glue DataBrew:** Visual data preparation tool.

  ![AWS Glue DataBrew Interface Showing Project](images/figure_26_part2.png)

  *Note:* Highlights no-code interactive data transformation workspace.

- **AWS Glue Data Catalog:** Central metadata repository.
- **Amazon Athena:** Serverless query service.

  ![Athena SQL Query for Aggregating Licence Data by Year](images/figure_30_part2.png)

  *Note:* SQL-based querying directly over S3-integrated datasets.

- **AWS KMS:** Encrypts data to meet compliance requirements.

  ![Creating Encryption Keys Using AWS KMS](images/figure_31_part2.png)

  *Note:* Symmetric encryption key creation for data protection.

- **Amazon CloudWatch:** Tracks metrics and logs.

  ![AWS CloudWatch Dashboard](images/figure_44_part2.png)

  *Note:* Dashboards monitor job success and failures.

- **AWS CloudTrail:** Logs all actions on AWS resources.

  ![AWS CloudTrail Logging](images/figure_45_part2.png)

  *Note:* Logs for accountability and audit compliance.

- **Amazon IAM:** Defines fine-grained access policies.

---

## Deliverables

- **Cleaned Data Lake (S3 Buckets):**

  ![System-Level Analytical Output in Parquet Format](images/figure_28_part2.png)

  *Note:* Displays analytics-ready business licence data stored in Amazon S3.

- **DataBrew Transformation Recipe:**

  ![Execution of AWS Glue DataBrew Job](images/figure_27_part2.png)

  *Note:* Validated transformation process and query-ready dataset.

- **Athena Query Set:**

  ![Athena SQL Query](images/figure_30_part2.png)

  *Note:* Interactive querying to summarize annual licensing metrics.

- **Analytical Visualizations:**

  ![Business Licensing Trends](images/figure_28_part1.png)

  *Note:* Displays annual licence counts and total fees collected.

- **Documentation & Presentation:** This README and an accompanying slide deck detailing project approach, architecture, and key insights.

---

## Insights & Findings

### Business Licensing Activity Patterns

![Business Licensing Activity Patterns](images/figure_28_part1.png)

*Note:* Highlights economic fluctuations and growth trends.

- **Dominant Business Categories:** Office, Retail, and Food Services dominated licences.
- **Geographical Distribution:** Downtown had highest concentration of licences.
- **Business Survival & Turnover:** Most businesses renewed licences year to year.
- **Economic Impact:** Vancouver collected over $80M in licence fees from 2013–2023.

---

## Connect With Me

- **LinkedIn:** [Barkha Kukreja](https://www.linkedin.com/in/barkhakukreja/)
