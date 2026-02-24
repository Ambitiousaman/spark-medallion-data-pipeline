# 🚀 Spark Medallion Data Pipeline

An end-to-end **Data Engineering pipeline** built using **PySpark, Docker, and Medallion Architecture** to simulate a production-grade distributed data processing workflow.

This project demonstrates schema enforcement, distributed processing, layered data architecture, and analytics integration.

---

## 🏗 Architecture Overview

The pipeline follows the **Medallion Architecture** pattern:

Raw (CSV) → Bronze (Schema Enforced) → Silver (Cleaned & Validated) → Gold (Aggregated Business Layer)

---

## ⚙️ Tech Stack

- 🐍 Python – Synthetic Data Generation  
- ⚡ PySpark – Distributed Data Processing  
- 🐳 Docker – Spark Cluster Deployment  
- 🧱 Medallion Architecture – Layered Data Design  
- 📦 Parquet – Optimized Columnar Storage  
- 📊 Power BI – Analytics & Visualization  

---

## 🖥 Distributed Spark Cluster

The pipeline runs on a Dockerized Spark cluster:

- 1 Spark Master  
- 2 Spark Workers  
- Shared volume for data storage  
- Spark UI enabled for monitoring  

This setup simulates a real distributed data processing environment.

---

## 📂 Data Flow

### 1️⃣ Raw Layer
- Synthetic retail dataset generated using Python  
- Stored as CSV  
- No transformation applied  

### 2️⃣ Bronze Layer
- Schema enforced during ingestion  
- Converted from CSV → Parquet  
- Structured and standardized  

### 3️⃣ Silver Layer
Data quality validations applied:
- Removed duplicate transaction IDs  
- Filtered invalid quantities and prices  
- Validated discount ranges  
- Standardized categorical values  
- Fixed date inconsistencies  

Result: Clean, analytics-ready dataset.

### 4️⃣ Gold Layer
- Business aggregations (Revenue, KPIs, City-level metrics)  
- Optimized for BI consumption  

---

## ▶️ How to Run the Project

### 1️⃣ Start Spark Cluster
```bash
docker-compose up -d
2️⃣ Generate Raw Data
python generate_raw_data.py

3️⃣ Run Spark Job
docker exec -it spark-master spark-submit /app/etl_pipeline.py

4️⃣ Monitor Spark UI
Open in your browser:
http://localhost:8080

📊 Analytics Layer
The Gold dataset is connected to Power BI for:
Revenue Analysis
City-Level Sales Mapping
KPI Dashboarding

🔥 Key Data Engineering Concepts Implemented

Schema enforcement during ingestion
Distributed transformations with Spark
Parquet optimization over CSV
Data validation & quality rules
Containerized big data environment
Layered storage architecture

🎯 Learning Outcomes

This project strengthened my understanding of:
Distributed Spark processing
Storage optimization techniques
Real-world data pipeline architecture
Docker-based cluster deployment
Medallion data modeling principles

🚀 Future Improvements

Incremental data loads
Partitioning strategies
Airflow orchestration
CI/CD integration
Cloud deployment (AWS / Azure)
