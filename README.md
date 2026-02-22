# aws-snowflake-powerBi-agriculture-pipeline
# 🌾 Agricultural Data Engineering Pipeline 
### AWS S3 ➔ Snowflake ➔ Power BI

> **"A cloud-native ETL pipeline designed to ingest and transform agricultural data. This project showcases the transition from a raw data lake in AWS S3 to a highly structured analytical layer in Snowflake, enabling granular insights into crop performance and climate trends."**

---

## 🛠️ Tech Stack
* **Cloud Infrastructure:** AWS S3 (Data Lake), AWS IAM (Identity & Access Management)
* **Data Warehouse:** Snowflake (Storage Integration & ETL)
* **SQL Dialect:** Snowflake SQL
* **Business Intelligence:** Power BI

---
## 🏗️ Data Transformation & Engineering (SQL)
After the initial ingestion from AWS S3, I performed several critical transformations in Snowflake to prepare the data for visualization. 

### 1. Data Normalization & Correction
To account for specific analysis parameters, I adjusted the raw figures using scalar operations:
* **Rainfall Adjustment:** Increased all rainfall values by 10% (`1.1 * rainfall`) to simulate specific climate scenarios.
* **Area Adjustment:** Scaled down the area figures by 10% (`0.9 * area`) for data normalization.

