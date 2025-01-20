# Swiggy-Snowflake: End-to-End Data Pipeline

## Overview
Swiggy-Snowflake is a complete data pipeline that processes raw CSV data and moves it into Snowflake. The pipeline follows a **Stage → Clean → Consumption** approach, transforming data into structured tables. A Streamlit dashboard then visualizes key performance indicators (KPIs) for daily, monthly, and yearly insights.

🔗 **View the project on SnowSight:** [SnowSight Link](https://app.snowflake.com/jpujfls/qd31171/#/swiggy-fEkcwawxs)

---
## 📌 Table of Contents
1. [Introduction](#introduction)
2. [Architecture](#architecture)
3. [Setup Requirements](#setup-requirements)
4. [Snowflake Components](#snowflake-components)
5. [Data Processing Workflow](#data-processing-workflow)
6. [Streamlit Dashboard](#streamlit-dashboard)

---

## 1️⃣ Introduction
This project showcases a **real-world data pipeline** for a food delivery service, simulating order processing, menu management, and user activity. Data is ingested, cleaned, transformed, and stored in structured Snowflake tables for analytics.

## 2️⃣ Architecture
The pipeline follows a structured multi-layered approach:
- **Stage Layer:** Raw CSV data is loaded into Snowflake using the `COPY` command.
- **Clean Layer:** Data is validated, merged, and structured with proper data types (SCD1 patterns).
- **Consumption Layer:** Fact and dimension tables are created, applying SCD2 patterns where needed.

🚀 **Flow:**  
📂 Raw CSV Files → 🏗 Stage Tables → 🔄 Merge & Clean → 📊 Fact & Dimension Tables → 📈 KPI Views

## 3️⃣ Setup Requirements
### **Prerequisites**
- A **Snowflake Account** (Free Trial or Enterprise)
- **Python 3.8+** (for Streamlit application)
- **Required Packages:**  
  ```bash
  pip install streamlit pandas snowflake-snowpark-python
  ```

## 4️⃣ Snowflake Components
The project defines multiple Snowflake objects:
- **Warehouse:** `SWIGGY_WH`
- **Database & Schemas:**
  - `SWIGGY` (Main database)
  - `STAGE_SCH` (Raw Data)
  - `CLEAN_SCH` (Processed Data)
  - `CONSUMPTION_SCH` (Final Analytics Layer)
- **Tables & Views:**
  - **Stage Tables:** Mirror the original CSV format.
  - **Clean Tables:** Define structured columns and apply data transformations.
  - **Fact & Dimension Tables:** Maintain historical data and track key business metrics.
  - **KPI Views:** Precomputed aggregations for quick insights.

## 5️⃣ Data Processing Workflow
1. **Ingestion:** CSV data is loaded into Snowflake using `COPY INTO`.
2. **Data Cleaning:** `MERGE` statements apply formatting, validation, and deduplication.
3. **Dimensional Modeling:** Fact and dimension tables are created using **SCD Type 2** methods.
4. **KPI Generation:** Views aggregate daily, monthly, and yearly performance metrics.

## 6️⃣ Streamlit Dashboard
The dashboard provides:
✅ **Real-time Snowflake Data Querying**  
✅ **Aggregated KPI Metrics & Charts**  
✅ **Filters for Monthly/Yearly Comparisons**  

📌 Run the Streamlit app:
```bash
streamlit run app.py
```

---
### 🚀 Future Enhancements
- Automate ingestion using Snowflake **Task Scheduling**
- Integrate **AI-powered insights** for advanced analytics

---
This project brings **real-world data warehousing** and **interactive analytics** into a single streamlined workflow! 🎯

