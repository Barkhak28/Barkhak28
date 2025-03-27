# Transforming Open Data into Actionable Insights: A Cloud Architecture Case

## Cloud Computing & Business Insights: CloudCatalyst Portfolio

### Project Overview
**CloudCatalyst Portfolio** demonstrates leveraging **AWS Cloud Computing** to transform open data into strategic insights. The project involved designing and deploying a cloud-native Data Analytic Platform (DAP) on AWS for analyzing the City of Vancouver’s business license data (2013–2024). This comprehensive solution illustrates skills in data ingestion, cleansing, analytics, security, and governance, providing meaningful insights to policymakers and stakeholders.

### Objectives
- **Cloud-Native Pipeline:** Build a scalable, serverless analytics pipeline.
- **Data Preparation & Analysis:** Clean, profile, and analyze business license data.
- **Security & Governance:** Implement data encryption, access control, and monitoring.
- **AWS Proficiency Showcase:** Demonstrate AWS expertise (S3, Glue, Athena, KMS, CloudWatch, CloudTrail).
- **Deliver Business Insights:** Provide actionable insights for policy-makers using visualizations and analytical summaries.

### Dataset Source & Description
Sourced from the City of Vancouver's Open Data Portal, this dataset includes comprehensive records of business licences issued from 2013 to May 2024. It features license numbers, business names, types, issuance dates, expiry dates, and anonymized location data.

### Cloud Architecture Overview
The architecture utilizes AWS services in a fully-managed, serverless configuration for ease of use, scalability, and robustness:

- **Amazon S3:** Central storage (Data Lake) for raw, processed, and analytical outputs. *(Figure No. #32, Part 1: S3 Bucket Showing Uploaded File)*
- **AWS Glue DataBrew:** Visual data profiling and interactive data cleaning.
- **AWS Glue Data Catalog:** Metadata management and schema cataloguing.
- **Amazon Athena:** Serverless querying and analytics directly on S3-stored data.
- **AWS KMS:** Encryption and secure data storage management.
- **AWS CloudTrail:** Comprehensive operational and security logging.
- **Amazon CloudWatch:** Real-time monitoring, alerts, and dashboards.

### Project Execution

#### Phase 1: Data Platform Setup & Summarization
Focused on establishing the DAP by securely ingesting, profiling, cleaning, cataloguing data, and performing exploratory analysis using AWS Glue and Athena.

*(Insert Figure No. #32 from Part 1: “S3 Bucket Showing Uploaded File”)*  
*(Add additional relevant figures: DataBrew Profiling, Glue Crawlers, Athena Queries.)*

#### Phase 2: Advanced Analysis, Security & Monitoring
Built upon Phase 1 to refine insights and fortify the platform with advanced security measures and monitoring:

- **Deeper Analysis:** Used Athena to uncover detailed trends (e.g., license growth by neighborhoods).
- **Data Security:** Implemented KMS encryption and bucket replication.
- **Data Governance:** Ensured data quality checks and governance with Glue’s visual ETL.
- **Real-Time Monitoring:** Established CloudWatch dashboards and CloudTrail for compliance.

*(Insert Figure from Part 2: Figure No. #41 - "CloudWatch Dashboard for Project Metrics")*

### Key Insights & Outputs
Insights derived revealed the pandemic’s significant impact on business licensing, the rapid growth in personal services licenses, and shifting business demographics across Vancouver. Detailed visual analytics provide stakeholders with actionable insights.

- *(Insert Figure from Part 1: Figure No. #28 - "Year-by-Year Business Licensing Trends")*

### Reflections & Professional Growth
This project significantly enhanced my understanding of cloud analytics, security best practices, and effective data governance. It taught me practical solutions for managing large-scale data securely, efficiently, and cost-effectively.

### Tools & Technologies Used
- **Data Storage & Management:** Amazon S3
- **Data Cleaning & Profiling:** AWS Glue DataBrew
- **Data Cataloging & Schema Management:** AWS Glue Data Catalog & Crawlers
- **Query & Analysis:** Amazon Athena
- **Security & Compliance:** AWS KMS, AWS IAM
- **Monitoring & Logging:** Amazon CloudWatch, AWS CloudTrail

### Connect with Me
Thank you for reviewing this project! I'm keen to collaborate or discuss this work further. Connect with me on [LinkedIn](your-link-here).

_This CloudCatalyst Portfolio demonstrates deep analytical expertise and strategic implementation of AWS to provide insightful, actionable business analytics for the City of Vancouver’s business licensing operations._
