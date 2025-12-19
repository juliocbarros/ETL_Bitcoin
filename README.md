# 🚀 Bitcoin ETL Data Pipeline

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![PySpark](https://img.shields.io/badge/PySpark-3.x-orange.svg)
![Databricks](https://img.shields.io/badge/Databricks-Platform-red.svg)
![Delta Lake](https://img.shields.io/badge/Delta%20Lake-2.0+-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

**Production-ready Data Engineering project that builds an automated ETL pipeline to ingest real-time cryptocurrency and FX data, process it at scale, and deliver analytics-ready data for dashboards.**

Built with **Python**, **PySpark**, **Databricks**, **Unity Catalog**, and **Delta Lake**.

[📖 Documentation](#-about-the-project) • [🚀 Quick Start](#-installation-and-setup) • [🏗️ Architecture](#️-architecture) • [📊 Examples](#-sql-query-examples)

</div>

---

## 📋 Table of Contents

- [📖 About the Project](#-about-the-project)
- [✨ Features](#-features)
- [🏗️ Architecture](#️-architecture)
- [🎯 Business Use Case](#-business-use-case)
- [🔄 ETL Workflow](#-etl-workflow)
- [📊 Data Model](#-data-model)
- [🛠️ Prerequisites](#️-prerequisites)
- [🚀 Installation and Setup](#-installation-and-setup)
- [💻 Usage](#-usage)
- [📈 SQL Query Examples](#-sql-query-examples)
- [⚙️ Automation and Orchestration](#️-automation-and-orchestration)
- [🔐 Security and Best Practices](#-security-and-best-practices)
- [📂 Repository Structure](#-repository-structure)
- [🧰 Tech Stack](#-tech-stack)
- [🧠 Skills Demonstrated](#-skills-demonstrated)
- [🤝 Contributing](#-contributing)
- [📝 License](#-license)

---

## 📖 About the Project

This project implements a complete and automated ETL pipeline for ingesting, processing, and storing cryptocurrency (Bitcoin) and exchange rate data. The pipeline is designed to be scalable, reliable, and production-ready, utilizing modern data engineering best practices.

### 🔍 Project Summary (TL;DR)

- 🔄 **End-to-End ETL Pipeline**: Automated extraction, transformation, and loading
- 🌐 **Real-time API Ingestion**: Up-to-date data from public APIs
- ⚙️ **Automated with Databricks Workflows**: Scheduled or manual execution
- 🧱 **ACID-compliant Delta Tables**: Guaranteed consistency and integrity
- 📊 **SQL Analytics Layer**: Ready for dashboards and BI
- ☁️ **Cloud-native Architecture**: Scalable and resilient

---

## ✨ Features

- ✅ **Real-time Ingestion**: Captures Bitcoin and exchange rate data via APIs
- ✅ **Distributed Processing**: Uses PySpark for large-scale processing
- ✅ **Multi-format Storage**: Supports JSON, Parquet, and Delta Tables
- ✅ **Time Travel**: Access historical data versions with Delta Lake
- ✅ **Schema Evolution**: Automatic schema evolution without breaking pipelines
- ✅ **Data Governance**: Unity Catalog for centralized management
- ✅ **ACID Transactions**: Guaranteed transactional consistency
- ✅ **Monitoring**: Execution logs and metrics

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    Data Sources                              │
├─────────────────────────────────────────────────────────────┤
│  Coinbase API          │    CurrencyFreaks API             │
│  (Bitcoin Price USD)   │    (USD → BRL Exchange Rate)       │
└────────────┬───────────────────────┬────────────────────────┘
             │                       │
             └───────────┬───────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│              PySpark ETL Processing                         │
│  • Data Extraction                                          │
│  • Currency Conversion (USD → BRL)                          │
│  • Data Transformation & Enrichment                         │
│  • Schema Standardization                                   │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│         Delta Lake (Unity Catalog)                           │
│  • Catalog: pipeline_api_bitcoin                            │
│  • Schema: biticoin_delta                                   │
│  • Table: btc_data                                          │
│  • Volume: raw_files (JSON/Parquet)                         │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│              SQL Analytics Layer                            │
│  • Real-time Queries                                        │
│  • Historical Analysis                                      │
│  • Dashboard Integration                                    │
└─────────────────────────────────────────────────────────────┘
```

### Main Components

1. **Extraction (Extract)**
   - Coinbase API: Bitcoin price in USD
   - CurrencyFreaks API: USD → BRL exchange rate

2. **Transformation (Transform)**
   - Currency conversion (USD → BRL)
   - Data type normalization
   - Timestamp enrichment
   - Schema standardization

3. **Loading (Load)**
   - Multi-format storage:
     - **JSON**: Human-readable raw data
     - **Parquet**: Optimized columnar format
     - **Delta Table**: ACID-compliant format with time travel

4. **Analytics**
   - Direct SQL queries on Delta Tables
   - Integration with BI tools
   - Real-time dashboards

---

## 🎯 Business Use Case

This pipeline was developed to meet the following business needs:

- 📈 **Trend Tracking**: Monitor Bitcoin prices in Brazilian Real (BRL)
- 📚 **Complete History**: Maintain historical price data with full auditability
- ⚡ **Real-time Monitoring**: Enable real-time analysis and alerts
- 📊 **Advanced Analytics**: Support complex analysis and executive dashboards
- 🔄 **Scalability**: Designed to scale from small workloads to Big Data

---

## 🔄 ETL Workflow

### 1️⃣ Extract (Extraction)

**Data Sources:**
- **Bitcoin Price (USD)**: Extracted from [Coinbase API](https://api.coinbase.com/v2/prices/spot)
- **USD → BRL Exchange Rate**: Extracted from [CurrencyFreaks API](https://api.currencyfreaks.com/)

**Features:**
- Robust API handling (JSON parsing, error handling)
- Retry logic for resilience
- Data validation on ingestion

### 2️⃣ Transform (Transformation)

**Operations Performed:**
- ✅ Currency conversion (USD → BRL)
- ✅ Data type normalization
- ✅ Timestamp enrichment
- ✅ Schema standardization
- ✅ Data validation

**Transformation Example:**
```python
valor_brl = valor_usd * taxa_usd_brl
timestamp = datetime.now()
```

### 3️⃣ Load (Loading)

**Storage Destinations:**

1. **Raw Volume (JSON/Parquet)**
   - Location: `/Volumes/pipeline_api_bitcoin/lakehouse/raw_files/`
   - Format: JSON and Parquet
   - Purpose: Raw data for auditing and reprocessing

2. **Delta Table**
   - Location: `pipeline_api_bitcoin.biticoin_delta.btc_data`
   - Format: Delta Lake
   - Mode: Incremental append (historical tracking)
   - Schema Evolution: Enabled

**Features:**
- ✅ Incremental append for complete history
- ✅ Schema evolution enabled
- ✅ ACID transactions guaranteed
- ✅ Time travel available

---

## 📊 Data Model

### Delta Table Schema: `btc_data`

| Column | Type | Description |
|--------|------|-------------|
| `valor_usd` | `DOUBLE` | Bitcoin price in USD |
| `valor_brl` | `DOUBLE` | Bitcoin price in BRL (calculated) |
| `criptomoeda` | `STRING` | Cryptocurrency code (BTC) |
| `moeda_original` | `STRING` | Original price currency (USD) |
| `taxa_conversao_usd_brl` | `DOUBLE` | USD → BRL exchange rate used |
| `timestamp` | `TIMESTAMP` | Ingestion timestamp |

### Record Example

```json
{
  "valor_usd": 43250.50,
  "valor_brl": 215000.00,
  "criptomoeda": "BTC",
  "moeda_original": "USD",
  "taxa_conversao_usd_brl": 4.97,
  "timestamp": "2024-01-15T10:30:45.123456"
}
```

---

## 🛠️ Prerequisites

Before getting started, make sure you have:

- ✅ **Databricks Workspace**: Access to a Databricks workspace (Community Edition or higher)
- ✅ **Python 3.8+**: Compatible Python version
- ✅ **Coinbase API Access**: Public access (no authentication required)
- ✅ **CurrencyFreaks API Key**: API key for CurrencyFreaks (get it at [currencyfreaks.com](https://currencyfreaks.com))
- ✅ **Python Libraries**:
  - `requests`
  - `pandas`
  - `pyspark` (provided by Databricks)

---

## 🚀 Installation and Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd ETL_Bitcoin
```

### 2. Configure Databricks

1. Access your Databricks workspace
2. Create a new notebook or import the existing notebook
3. Attach the notebook to a Databricks cluster

### 3. Configure APIs

#### CurrencyFreaks API Key

⚠️ **Important**: Never hardcode API keys in code!

**Option 1: Use Databricks Secrets (Recommended)**
```python
# In Databricks, configure the secret:
# Databricks CLI: databricks secrets create-scope --scope bitcoin-pipeline
# databricks secrets put --scope bitcoin-pipeline --key currencyfreaks-api-key

# In code:
api_key = dbutils.secrets.get(scope="bitcoin-pipeline", key="currencyfreaks-api-key")
```

**Option 2: Environment Variables**
```python
import os
api_key = os.environ.get('CURRENCYFREAKS_API_KEY')
```

### 4. Configure Unity Catalog

Execute the SQL cells in the notebook to create the infrastructure:

```sql
-- Create Catalog
CREATE CATALOG IF NOT EXISTS pipeline_api_bitcoin
COMMENT 'Catalog for pipeline api Bitcoin';

-- Create Schema for Delta Tables
CREATE SCHEMA IF NOT EXISTS pipeline_api_bitcoin.biticoin_delta
COMMENT 'Lakehouse schema to store delta data';

-- Create Schema for Lakehouse
CREATE SCHEMA IF NOT EXISTS pipeline_api_bitcoin.lakehouse
COMMENT 'Lakehouse schema to store processed data';

-- Create Volume for raw files
CREATE VOLUME IF NOT EXISTS pipeline_api_bitcoin.lakehouse.raw_files
COMMENT 'Volume for raw files from initial ingestion';
```

### 5. Install Dependencies

In the Databricks notebook, execute:

```python
%pip install requests pandas
```

---

## 💻 Usage

### Manual Execution

1. Open the notebook `src/Get_Biticoin.ipynb` in Databricks
2. Execute all cells sequentially
3. Data will be extracted, transformed, and loaded automatically

### Workflow Execution (Recommended)

1. **Create Job in Databricks**:
   - Go to **Workflows** → **Create Job**
   - Add the notebook as a task
   - Configure parameters if needed

2. **Configure Schedule** (Optional):
   - Set up a cron schedule (e.g., `0 */1 * * *` to run every hour)
   - Or execute manually when needed

3. **Monitor Executions**:
   - Track logs and metrics in the Databricks interface
   - Set up alerts for failures

### Main Code Example

```python
# 1. Extract data
dados_bitcoin = Extract_Bitcoin_Data()
dados_cotacao = extrair_cotacao_usd_brl()

# 2. Extract conversion rate
taxa_usd_brl = float(dados_cotacao['rates']['BRL'])

# 3. Transform data
dados_bitcoin_tratado = tratar_dados_bitcoin(dados_bitcoin, taxa_usd_brl)

# 4. Create DataFrame
df_bitcoin = pd.DataFrame(dados_bitcoin_tratado)

# 5. Save in multiple formats
# JSON and Parquet (raw files)
# Delta Table (analytics-ready)
```

---

## 📈 SQL Query Examples

### Latest Bitcoin Price

```sql
SELECT 
    valor_usd,
    valor_brl,
    timestamp
FROM pipeline_api_bitcoin.biticoin_delta.btc_data
ORDER BY timestamp DESC
LIMIT 1;
```

### Historical Maximum Price

```sql
SELECT 
    MAX(valor_brl) AS preco_maximo_brl,
    MAX(valor_usd) AS preco_maximo_usd,
    MAX(timestamp) AS data_maximo
FROM pipeline_api_bitcoin.biticoin_delta.btc_data;
```

### Historical Minimum Price

```sql
SELECT 
    MIN(valor_brl) AS preco_minimo_brl,
    MIN(valor_usd) AS preco_minimo_usd,
    MIN(timestamp) AS data_minimo
FROM pipeline_api_bitcoin.biticoin_delta.btc_data;
```

### Temporal Evolution (Last 24 Hours)

```sql
SELECT 
    DATE_TRUNC('hour', timestamp) AS hora,
    AVG(valor_brl) AS preco_medio_brl,
    AVG(valor_usd) AS preco_medio_usd,
    COUNT(*) AS registros
FROM pipeline_api_bitcoin.biticoin_delta.btc_data
WHERE timestamp >= CURRENT_TIMESTAMP - INTERVAL 24 HOURS
GROUP BY DATE_TRUNC('hour', timestamp)
ORDER BY hora DESC;
```

### Volatility Analysis

```sql
SELECT 
    DATE(timestamp) AS data,
    MIN(valor_brl) AS minimo_brl,
    MAX(valor_brl) AS maximo_brl,
    AVG(valor_brl) AS media_brl,
    (MAX(valor_brl) - MIN(valor_brl)) / AVG(valor_brl) * 100 AS volatilidade_percentual
FROM pipeline_api_bitcoin.biticoin_delta.btc_data
GROUP BY DATE(timestamp)
ORDER BY data DESC
LIMIT 30;
```

### Time Travel - Access Previous Version

```sql
-- View version history
DESCRIBE HISTORY pipeline_api_bitcoin.biticoin_delta.btc_data;

-- Access specific version (e.g., version 5)
SELECT * FROM pipeline_api_bitcoin.biticoin_delta.btc_data 
VERSION AS OF 5;
```

---

## ⚙️ Automation and Orchestration

### Databricks Workflows

The pipeline can be automated using Databricks Jobs & Workflows:

**Features:**
- ✅ Parameterized execution (API Keys via secrets)
- ✅ Manual or scheduled execution (cron)
- ✅ Execution logs and monitoring
- ✅ Automatic retry on failure
- ✅ Email/Slack notifications

**Job Configuration Example:**

```json
{
  "name": "Bitcoin ETL Pipeline",
  "schedule": {
    "quartz_cron_expression": "0 */1 * * * ?",
    "timezone_id": "America/Sao_Paulo"
  },
  "tasks": [
    {
      "task_key": "extract_transform_load",
      "notebook_task": {
        "notebook_path": "/src/Get_Biticoin",
        "base_parameters": {}
      }
    }
  ]
}
```

---

## 🔐 Security and Best Practices

### Security

- ✅ **API Keys never hardcoded**: Always use Databricks Secrets or environment variables
- ✅ **Parameterized secrets in workflows**: Secure credential configuration
- ✅ **Data governance via Unity Catalog**: Centralized access control
- ✅ **ACID-compliant storage**: Guaranteed transactional consistency
- ✅ **Time travel for auditing**: Complete change traceability

### Implemented Best Practices

1. **Separation of Concerns**: Modular and reusable functions
2. **Error Handling**: Robust validation and exception handling
3. **Logging**: Detailed operation logging
4. **Schema Evolution**: Support for schema changes without breaking pipelines
5. **Incremental Loading**: Append mode for efficiency and complete history
6. **Multi-format Storage**: Flexibility for different use cases

---

## 📂 Repository Structure

```
ETL_Bitcoin/
│
├── README.md                 # Main documentation
│
└── src/
    └── Get_Biticoin.ipynb   # Main ETL pipeline notebook
        │
        ├── 1. Import Libraries
        ├── 2. Extract and Transform Data
        │   ├── Extract_Bitcoin_Data()
        │   ├── extrair_cotacao_usd_brl()
        │   └── tratar_dados_bitcoin()
        │
        ├── 3. Config Unity Catalog
        │   ├── Create Catalog
        │   ├── Create Schemas
        │   └── Create Volume
        │
        ├── 4. Create Pandas DataFrame
        ├── 5. Save to JSON
        ├── 6. Save to Parquet
        ├── 7. Convert to PySpark DataFrame
        ├── 8. Save as Delta Table
        ├── 9. Read Delta Table
        ├── 10. Query with SQL
        └── 11. Check Delta History (Time Travel)
```

---

## 🧰 Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **Python** | 3.8+ | Main programming language |
| **PySpark** | 3.x | Distributed data processing |
| **Pandas** | Latest | In-memory data manipulation |
| **Requests** | Latest | HTTP client for APIs |
| **Databricks** | Platform | Processing and orchestration platform |
| **Delta Lake** | 2.0+ | ACID-compliant storage format |
| **Unity Catalog** | Latest | Data governance and catalog |

### Format Comparison

| Format | Use Case | Advantages | Disadvantages |
|--------|----------|------------|---------------|
| **CSV** | Debugging, small datasets | Readable, universal | Large size, slow |
| **JSON** | Raw data, APIs | Readable, flexible | Large size, not optimized |
| **Parquet** | Big Data, analytics | Compact, fast, columnar | Binary, not readable |
| **Delta Table** | Data Warehouse, critical pipelines | ACID, time travel, schema evolution | Requires Delta support |

---

## 🧠 Skills Demonstrated

This project demonstrates proficiency in:

- ✅ **Data Engineering**: Building robust ETL pipelines
- ✅ **ETL/ELT Pipelines**: Data extraction, transformation, and loading
- ✅ **PySpark & Distributed Processing**: Large-scale distributed processing
- ✅ **Delta Lake & Data Lakehouse**: Modern data architecture
- ✅ **Databricks Workflows**: Automation and orchestration
- ✅ **SQL Analytics**: Analytical queries on structured data
- ✅ **API Integration**: REST API integration
- ✅ **Cloud Data Architecture**: Scalable cloud-native architecture
- ✅ **Data Governance**: Unity Catalog and data governance
- ✅ **Best Practices**: Security, versioning, and documentation

---

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. 🍴 Fork the project
2. 🌿 Create a branch for your feature (`git checkout -b feature/AmazingFeature`)
3. 💾 Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. 📤 Push to the branch (`git push origin feature/AmazingFeature`)
5. 🔀 Open a Pull Request

### Contribution Guidelines

- Follow existing code standards
- Add tests for new features
- Update documentation as needed
- Keep commits descriptive and organized

---




