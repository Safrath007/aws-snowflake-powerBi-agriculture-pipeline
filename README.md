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

### 2. Feature Engineering (Categorization)
I engineered two new categorical features to allow for better "slicing" in the Power BI dashboard:

* **Year Groups:** Created a `Year_Group` column to segment data into specific eras:
    * **Y1:** 2004 – 2009
    * **Y2:** 2010 – 2015
    * **Y3:** 2016 – 2019
* **Rainfall Buckets:** Created a `rainfall_groups` column to classify moisture levels:
    * **Low:** 255mm to < 1200mm
    * **Medium:** 1200mm to < 2800mm
    * **High:** 2800mm to 4103mm

---
## 📊 Dashboard Insights
The resulting Power BI dashboard (connected via Snowflake) reveals:
* **Seasonal Consistency:** Average rainfall remains remarkably steady across Rabi, Kharif, and Zaid seasons (~3070mm to 3105mm).
* **Crop Sensitivity:** Paddy and Arecanut are the highest moisture-consuming crops, requiring over 5.5K average rainfall.
* **Top Locations:** Bangalore and Karwar emerged as the highest rainfall regions in the dataset.

### Dashboard Preview
![Agriculture Analysis Dashboard](./power-bi/dashboard_ss.png)

---

## 📊 Dashboard Insights
The resulting Power BI dashboard (connected via Snowflake) reveals:
* **Seasonal Consistency:** Average rainfall remains remarkably steady across Rabi, Kharif, and Zaid seasons (~3070mm to 3105mm).
* **Crop Sensitivity:** Paddy and Arecanut are the highest moisture-consuming crops, requiring over 5.5K average rainfall.
* **Top Locations:** Bangalore and Karwar emerged as the highest rainfall regions in the dataset.

### Dashboard Preview
![Agriculture Analysis Dashboard](./power-bi/dashboard_ss.png)

---
## 📝 How to Replicate
1.  **AWS Setup:** Upload your data to S3 and configure the IAM Role ARN.
2.  **Snowflake Integration:** Run the `CREATE STORAGE INTEGRATION` script provided in the `/sql` folder.
3.  **ETL Process:** Execute the DDL and DML scripts to load and transform the `Agriculture` table.
4.  **Power BI:** Connect to your Snowflake warehouse to view the pre-modeled data.
