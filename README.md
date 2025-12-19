🚀 Bitcoin ETL Data Pipeline | PySpark • Databricks • Delta Lake

Production-ready Data Engineering project that builds an automated ETL pipeline to ingest real-time cryptocurrency and FX data, process it at scale, and deliver analytics-ready data for dashboards.

Built with Python, PySpark, Databricks, Unity Catalog, and Delta Lake.

🔍 Project Summary (TL;DR)

🔄 End-to-End ETL Pipeline

🌐 Real-time API ingestion

⚙️ Automated with Databricks Workflows

🧱 ACID-compliant Delta Tables

📊 Analytics & dashboard-ready SQL layer

☁️ Cloud-native, scalable architecture

🏗️ Architecture Overview
Coinbase API + CurrencyFreaks API
              ↓
        PySpark ETL
              ↓
   Delta Lake (Unity Catalog)
              ↓
        SQL Analytics
              ↓
          Dashboard

🎯 Business Use Case

Track Bitcoin price trends in Brazilian Real (BRL)

Maintain historical price data with full auditability

Enable real-time monitoring and analytics

Designed to scale from small workloads to Big Data

🔄 ETL Workflow
1️⃣ Extract

Bitcoin price (USD) from Coinbase API

USD → BRL exchange rate from CurrencyFreaks

Robust API handling (JSON parsing, error handling)

2️⃣ Transform

Currency conversion (USD → BRL)

Data type normalization

Timestamp enrichment

Schema standardization

3️⃣ Load

Stored as Delta Tables in Databricks

Managed with Unity Catalog

Incremental append (historical tracking)

Schema evolution enabled

📊 Data Model (Delta Table)
Column	Type	Description
valor_usd	DOUBLE	Bitcoin price (USD)
valor_brl	DOUBLE	Bitcoin price (BRL)
criptomoeda	STRING	BTC
moeda_original	STRING	USD
taxa_conversao_usd_brl	DOUBLE	FX rate
timestamp	TIMESTAMP	Ingestion time
📈 Analytics & Dashboard Queries

Latest Bitcoin price

Historical max price

Historical min price

Time-series price evolution

All analytics are powered by SQL directly on Delta Lake, enabling fast queries and BI integration.

⚙️ Automation & Orchestration

Databricks Jobs & Workflows

Parameterized execution (API Keys)

Manual or scheduled runs

Execution logs and monitoring

🧰 Tech Stack

Python 3.8+

PySpark

Requests

Databricks

Delta Lake

Unity Catalog

📂 Repository Structure
pipeline-api-bitcoin-com-databricks/
├── src/
│   ├── get_bitcoin_full.py      # Full ETL with documentation
│   ├── get_bitcoin_macro.py     # Production workflow version
│   ├── aquecimento_python.py    # Python fundamentals
│   └── aquecimento_sql.py       # SQL fundamentals
├── img/
│   └── cover.png
├── README.md
└── .gitignore

🔐 Security & Best Practices

API keys never hardcoded

Parameterized secrets in workflows

Governed data access via Unity Catalog

ACID-compliant storage with time travel

🧠 Skills Demonstrated

✔ Data Engineering
✔ ETL / ELT Pipelines
✔ PySpark & Distributed Processing
✔ Delta Lake & Data Lakehouse
✔ Databricks Workflows
✔ SQL Analytics
✔ API Integration
✔ Cloud Data Architecture
