# 📈 Real-Time Stocks Market Data Pipeline
 
This project demonstrates an **end-to-end real-time data engineering solution** built using the **Modern Data Stack**.

It captures **live stock market data** from an external API (due to API rate limits, data frequency depends on the Finnhub free tier), streams it in real time, orchestrates transformations, and delivers analytics-ready insights — all within a single, unified architecture.

This project is designed as a **portfolio-grade implementation** to showcase skills in **Streaming Data Engineering, Cloud Data Warehousing, ETL/ELT pipelines, and Analytics Engineering**.


---

## 📌 Project Overview

This project demonstrates an **end-to-end real-time data pipeline** using the **Modern Data Stack**.

**Key objectives:**
- Capture **live stock market data** (not simulated)
- Stream data in real time using Kafka
- Orchestrate ingestion and transformations
- Build analytics-ready datasets
- Visualize insights using Power BI

---

## 🏗️ Architecture
- This architecture follows the Medallion pattern (Bronze–Silver–Gold) to process real-time stock market data.
- Live data is ingested via Kafka and stored as raw events in the Bronze layer.
- DBT transformations in Snowflake clean and standardize data into the Silver layer.
- The Gold layer delivers analytics-ready models consumed by Power BI for real-time insights.

Below is the conceptual architecture for the real-time pipeline:

![Real-Time Stocks MDS Architecture](https://raw.githubusercontent.com/MOHDAKRAM43/real-time-stocks-mds/main/images/REAL-TIME-STOCKS-MDS-ARCHITECTURE.png)

---
## ⚡ Tech Stack

- **Snowflake** – Cloud Data Warehouse  
- **DBT** – SQL-based Transformations  
- **Apache Airflow** – Workflow Orchestration  
- **Apache Kafka** – Real-time Data Streaming  
- **Python** – API Integration & Streaming Logic  
- **Docker & Docker Compose** – Containerization  
- **MinIO** – S3-compatible Object Storage  
- **Power BI** – Data Visualization  

---

## ✅ Key Features

- Fetches **live stock market data** from an external API  
- Real-time streaming pipeline using **Apache Kafka**  
- Automated ETL workflow orchestrated by **Airflow**  
- **Medallion Architecture** (Bronze, Silver, Gold)  
- Transformations implemented using **DBT in Snowflake**  
- Scalable cloud warehouse powered by **Snowflake**  
- **Analytics-ready Power BI dashboards**  

---
```
## 📂 Repository Structure

real-time-stocks-mds/
├── consumer/           # Kafka consumer logic
├── producer/           # Finnhub API producer logic
├── dag/                # Airflow DAG definitions
├── dbt_stocks/         # dbt models (Bronze, Silver, Gold)
├── images/             # Documentation assets
├── docker-compose.yml  # Infrastructure as Code
└── requirements.txt    # Python dependencies

```

---

## 🚀 Getting Started

### Prerequisites
- Docker & Docker Compose  
- Python 3.9+  
- Snowflake Account  
- Finnhub API Key  
- Power BI Desktop  

---
```
Setup Steps

1. **Clone the Repository**
```bash
git clone https://github.com/MOHDAKRAM43/real-time-stocks-mds.git
cd real-time-stocks-mds

docker-compose up -d

python producer/producer.py

python consumer/consumer.py

docker-compose up -d
Run Kafka Producer

Fetches live stock prices

Streams data into Kafka

python producer/producer.py
Run Kafka Consumer

Consumes Kafka messages

Stores raw data in MinIO (Bronze layer)

python consumer/consumer.py
Airflow Orchestration

Trigger DAG: minio_to_snowflake

Loads data from MinIO into Snowflake Bronze tables

Scheduled every 1 minute
```
---
⚙️ Step-by-Step Implementation
1️⃣ Kafka Setup
Kafka configured locally using Docker

Created topic: stocks-topic

Handles real-time stock market events

2️⃣ Live Market Data Producer
Python-based Kafka producer

Fetches real-time stock prices from Finnhub API

Streams JSON-formatted data

3️⃣ Kafka Consumer → MinIO
Kafka consumer written in Python

Writes streaming data into MinIO buckets

Acts as the Bronze (Raw) layer

4️⃣ Airflow Orchestration
Apache Airflow initialized in Docker

DAG loads data into Snowflake

Fully automated and scheduled

5️⃣ Snowflake Warehouse Setup
Database, schema, and warehouse created

Implemented Bronze → Silver → Gold layers

6️⃣ DBT Transformations
DBT configured with Snowflake

Models include:

Bronze → Raw structured data

Silver → Cleaned and validated data

Gold → Analytical views (KPIs, Candlesticks, Tree Maps)

7️⃣ Power BI Dashboard
Connected to Snowflake Gold layer using DirectQuery
Built dashboards:

📈 Candlestick charts

🌳 Tree charts

🎯 KPI cards

📊 Gauge charts

📊 Final Deliverables
Automated real-time data pipeline

Kafka-based streaming ingestion

Snowflake Bronze–Silver–Gold tables

DBT transformation models

Airflow orchestration DAGs

Power BI dashboards with live insights

The following screenshot shows the Power BI dashboard with real-time analytics visuals:

![Real-Time MDS Power BI](https://raw.githubusercontent.com/MOHDAKRAM43/real-time-stocks-mds/main/images/REAL-TIME-MDS-POWERBI.png)

Connected to Snowflake **Gold layer** using DirectQuery, with real-time stock metrics and visuals including Candlestick charts, KPIs, and Gauge charts.

---
### 🔮 Future Enhancements

To further enhance scalability, reliability, and production readiness, the following improvements are planned:

Schema Registry
Introduce a Schema Registry (e.g., Confluent Schema Registry) to enforce schema evolution, ensure data consistency across producers and consumers, and prevent breaking changes in real-time streams.

Kafka Connect
Leverage Kafka Connect for standardized, scalable ingestion and sink connectors, reducing custom code and enabling easier integration with external systems such as cloud storage and databases.

CI/CD for DBT
Implement CI/CD pipelines for DBT models using GitHub Actions to automate testing, documentation generation, and deployments, ensuring reliable and version-controlled analytics engineering workflows.

Alerting & Monitoring
Add monitoring and alerting using tools like Prometheus, Grafana, or Airflow alerts to track pipeline health, detect failures, and ensure high availability of real-time data processing.

### 🧠 Key Learnings
Real-time streaming architecture design

Kafka producer & consumer patterns

Orchestrating pipelines using Airflow

DBT best practices for analytics engineering

Building scalable cloud data warehouses.

⭐ If you like this project, don’t forget to star the repository!


🔗 Connect With Me
[linkedin]: [https://www.linkedin.com/in/mohd-akram-6a210a259/]
[Github]: [(https://github.com/MOHDAKRAM43)]

