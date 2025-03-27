# 🚀 Cloud-Based Business Licencing Analytics Platform | City of Vancouver (2013–2024)

> **Capstone Project | Cloud Computing Portfolio**  
> Author: [Your Full Name]  
> Course: BUSI 653 – Cloud Computing  
> Data Source: [City of Vancouver Open Data Portal](https://opendata.vancouver.ca)  
> Tools Used: AWS EC2, S3, Glue, Athena, CloudWatch, CloudTrail, DataBrew, KMS  
> Timeline: 2013–2024

---

## 📘 Project Overview

This capstone project presents a full-stack AWS implementation of a data analytics platform for the **City of Vancouver's Business Licencing dataset (2013–2024)**. The solution integrates real-time ingestion, cleaning, transformation, analysis, data governance, and security.

🧭 **Objective**: To create a secure, automated, and analytically-ready data platform that enables decision-makers to explore trends, enforce data governance, and monitor performance through descriptive analytics.

---

## 📦 Dataset Description

The dataset includes over a decade of open licensing records from the City of Vancouver. Each record captures:

- 📄 **Licence Details**: Licence number, issue/expiry dates, status  
- 🏢 **Business Info**: Name, type, sub-type  
- 🌎 **Location**: Full address, postal code, coordinates  
- 👥 **Employee Info**: Count by gender, part/full-time  
- 🗓️ **Timeline**: 2013 to 2024  

---

## 🧩 System Architecture

### ✅ Phase 1: End-to-End Ingestion + Cleaning + Storage

> *Figure No. 1 (Part 1): AWS Architecture Overview*

- **EC2**: Used for secure transfer of raw files from operational teams  
- **Amazon S3**: Versioned and KMS-encrypted buckets for raw, cleaned, and transfer data  
- **AWS Glue DataBrew**: Profiling and cleaning operations with visual transformations  
- **AWS Glue Crawler + Catalog**: Metadata management for discoverability  
- **AWS Athena**: SQL-based querying of partitioned data  
- **AWS CloudTrail + CloudWatch**: Full-stack activity logging and performance monitoring  
- **KMS**: Central encryption for all data lifecycle stages  

---

## 🔍 Phase 2: Analytics + Governance + Monitoring

> *Figure No. 2 (Part 2): Visual ETL Governance Flow*  
> *Figure No. 3 (Part 2): CloudWatch Dashboard*

### 📊 Analytical Layer

- Built separate outputs for:
  - **System-Level (Parquet/Snappy)**: Efficient analytics processing  
  - **User-Level (CSV)**: Easy stakeholder access  
- Executed Athena SQL queries to extract:
  - Total licences issued by year  
  - Total fees collected (SumFeePaid)

### 🛡️ Data Governance

- Applied **3 Data Quality Rules** via Visual ETL:
  - Completeness (>95%)  
  - Uniqueness (>99%)  
  - Freshness (<1279 days)
- Used conditional routers to split data into:
  - ✅ Passed → Partitioned in S3  
  - ❌ Failed → Stored separately for rework

> *Figure No. 4 (Part 2): ETL Job – Data Quality Routing*  
> *Figure No. 5 (Part 2): Glue Job Success Output*

### 🖥️ Monitoring

- **CloudWatch Dashboard** for:
  - Bucket size metrics
  - Glue resource usage
  - Alarms with SNS notifications  
- **CloudTrail Logs**:
  - User actions
  - API usage
  - Service calls for auditability

---

## 🔐 Data Security Strategy

> *Figure No. 6 (Part 2): S3 Encryption and Versioning Setup*  
> *Figure No. 7 (Part 2): KMS Key Creation and Mapping*

- Server-side encryption (SSE-KMS) on all S3 buckets  
- Versioning for recovery and rollback  
- Cross-region replication for disaster resilience

---

## 🛠️ Technologies & AWS Services Used

| Code | Service             | Purpose                                                                 |
|------|----------------------|-------------------------------------------------------------------------|
| A    | **Amazon EC2**       | Raw file transfer point; secure CLI-based upload                       |
| B    | **Amazon S3**        | Primary storage with encryption, versioning, and tiered buckets        |
| C    | **AWS Glue**         | Visual ETL transformations, data quality checks, and metadata catalog  |
| D    | **DataBrew**         | Visual profiling, cleaning, and formatting                             |
| E    | **Athena**           | Query engine to summarize insights without infrastructure              |
| F    | **CloudWatch**       | Metric monitoring, dashboards, custom alerts                           |
| G    | **CloudTrail**       | Compliance and activity tracking logs                                  |
| H    | **KMS**              | Encryption key management for data-in-transit and at-rest              |
| I    | **SNS**              | Notification system for alerts                                         |

---

## 📈 Key Insights & Highlights

- 📅 **Peak years** for business licence issuance: 2016, 2019, and 2023  
- 🧾 **Sum of fees collected**: Clear growth trend tied to regulatory updates  
- 🧹 **Common data quality issues**: Missing expiry dates, duplicated licence numbers  
- 🔐 **Security**: Successfully implemented versioned, encrypted, and replicated buckets  
- 🧠 **Governance**: Automated filtering and separation of failed records for cleaning

---

## 🎯 Final Deliverables

- ✅ Functional AWS deployment (EC2, S3, Glue, Athena)  
- 📁 Secure storage layers with SSE-KMS and replication  
- 🔎 Descriptive analytics pipeline with SQL queries  
- 📊 Dashboards and metrics for governance and performance  
- 📚 Full documentation of methods, figures, and architecture  

---

## 🤝 Acknowledgements

This project was conducted under the **Cloud Computing Capstone (BUSI 653)** with support from the instructional team and data provided by the **City of Vancouver Open Data Portal**.

---

## 📂 Repository Structure

```bash
📁/figures/
    ├── Part1_AWS_Architecture.png
    ├── Part2_Glue_ETL_Job.png
📁/scripts/
    └── Athena_queries.sql
📁/docs/
    └── Report_Part1_Part2.pdf
README.md
