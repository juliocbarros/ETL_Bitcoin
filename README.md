# 🚀 Bitcoin ETL Data Pipeline (Databricks)

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![PySpark](https://img.shields.io/badge/PySpark-3.x-orange.svg)
![Databricks](https://img.shields.io/badge/Databricks-Platform-red.svg)
![Delta Lake](https://img.shields.io/badge/Delta%20Lake-2.0+-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

**Production-ready Data Engineering project that builds an automated ETL pipeline to ingest real-time cryptocurrency and FX data, process it at scale, and deliver analytics-ready data for dashboards.**

Built with **Python**, **PySpark**, **Databricks**, **Unity Catalog**, and **Delta Lake**.

[📖 Documentation](#-about-the-project) • [🚀 Quick Start](#-installation-and-setup) • [🏗️ Architecture](#️-architecture) • [📊 Dashboard](#-dashboard-visualization)

</div>

---

## 📋 Table of Contents

- [📖 About the Project](#-about-the-project)
- [🎯 What We're Building](#-what-were-building)
- [🎓 Learning Objectives](#-learning-objectives)
- [✨ Features](#-features)
- [🏗️ Architecture](#️-architecture)
- [🎯 Business Use Case](#-business-use-case)
- [🔄 ETL Workflow](#-etl-workflow)
- [📊 Data Model](#-data-model)
- [🛠️ Prerequisites](#️-prerequisites)
- [🚀 Installation and Setup](#-installation-and-setup)
- [💻 Usage](#-usage)
- [📈 Dashboard Queries](#-dashboard-queries)
- [⚙️ Jobs & Pipelines](#️-jobs--pipelines-orchestration)
- [📊 Dashboard Visualization](#-dashboard-visualization)
- [🔐 Security and Best Practices](#-security-and-best-practices)
- [📂 Repository Structure](#-repository-structure)
- [🧰 Tech Stack](#-tech-stack)
- [🧠 Skills Demonstrated](#-skills-demonstrated)
- [🎓 Workshop](#-workshop)
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
- 📊 **Interactive Dashboard**: Real-time visualization with metrics and charts
- ☁️ **Cloud-native Architecture**: Scalable and resilient

---

## 🎯 What We're Building

In this workshop, you will build a complete ETL pipeline that extracts data from APIs, transforms and stores it in Delta Tables, and creates an interactive dashboard for visualization.

### Complete Project Architecture

**Project Components:**
- 📥 **EXTRACT**: Data extraction from 2 APIs (Coinbase and CurrencyFreaks)
- 🔄 **TRANSFORM**: Currency conversion and data structuring
- 💾 **LOAD**: Storage in Delta Table in Unity Catalog
- ⚙️ **WORKFLOW**: Automation via Databricks Jobs & Pipelines
- 📊 **DASHBOARD**: Interactive visualization with metrics and charts

---

## 🎓 Learning Objectives

### General Objective

Teach practical Data Engineering fundamentals through building a complete ETL pipeline, from API data extraction to creating interactive dashboards, using modern technologies widely used in the market.

### Learning Goals

#### 1. Python Fundamentals for Data Engineering
- ✅ Variables and data types (string, int, float, bool, list, dict)
- ✅ Functions and methods (creation, reuse, string/list/dict methods)
- ✅ Data manipulation (data structures, iterations)
- ✅ API handling (HTTP requests, JSON, error handling)

**Why it's important?** Python is the most used language in Data Engineering. Mastering fundamentals is essential for building robust pipelines.

#### 2. SQL Fundamentals for Data Analysis
- ✅ SELECT, FROM, WHERE (basic queries)
- ✅ ORDER BY and LIMIT (ordering and limiting results)
- ✅ Alias (AS) (column renaming)
- ✅ Analytical queries (latest value, maximum, minimum, history)

**Why it's important?** SQL is the standard language for querying data. Every Data Engineer needs to know SQL to create dashboards, reports, and analyses.

#### 3. ETL (Extract, Transform, Load)
- ✅ **Extract**: Consume data from REST APIs
- ✅ **Transform**: Convert currencies, structure data, add metadata
- ✅ **Load**: Store data in optimized formats (Delta Lake)

**Why it's important?** ETL is the heart of Data Engineering. 90% of a Data Engineer's work is building and maintaining ETL pipelines.

#### 4. PySpark and Distributed Processing
- ✅ PySpark DataFrames (distributed data structure)
- ✅ Difference between Pandas and PySpark (when to use each)
- ✅ Large-scale processing (preparation for Big Data)

**Why it's important?** PySpark allows processing terabytes of distributed data in clusters. It's essential for real Big Data projects.

#### 5. Databricks and Unity Catalog
- ✅ Databricks Workspace (development environment)
- ✅ Unity Catalog (data governance: Catalog → Schema → Table)
- ✅ Interactive notebooks (development and documentation)

**Why it's important?** Databricks is one of the most used platforms in the market. Unity Catalog is the modern standard for data organization in Data Lakes.

#### 6. Delta Lake and ACID Storage
- ✅ Delta Tables (tables with ACID transactions)
- ✅ Time Travel (access to historical versions)
- ✅ Schema Evolution (automatic schema evolution)
- ✅ Incremental append (data history)

**Why it's important?** Delta Lake brings reliability and performance to Data Lakes. It's the modern standard for analytical data storage.

#### 7. Automation with Databricks Workflows
- ✅ Workflow creation (pipeline orchestration)
- ✅ Key-Value parameters (dynamic configuration)
- ✅ Scheduled execution (automated data collection)

**Why it's important?** Pipelines need to run automatically. Workflows allow orchestrating and scheduling executions without manual intervention.

#### 8. Visualization and Dashboards
- ✅ SQL queries for dashboards (4 main queries)
- ✅ Data visualization (charts, metrics, history)
- ✅ Trend analysis (temporal price evolution)

**Why it's important?** Data without visualization doesn't generate value. Dashboards allow stakeholders to make data-driven decisions.

### Final Workshop Result

At the end of the workshop, you will have built:

- ✅ Complete working ETL pipeline in production
- ✅ Practical knowledge of Python, SQL, PySpark, and Databricks
- ✅ Real portfolio to showcase in interviews
- ✅ Solid foundation to advance in Data Engineering

---

## ✨ Features

- ✅ **Real-time Ingestion**: Captures Bitcoin and exchange rate data via APIs
- ✅ **Distributed Processing**: Uses PySpark for large-scale processing
- ✅ **Multi-format Storage**: Supports JSON, Parquet, and Delta Tables
- ✅ **Time Travel**: Access historical data versions with Delta Lake
- ✅ **Schema Evolution**: Automatic schema evolution without breaking pipelines
- ✅ **Data Governance**: Unity Catalog for centralized management
- ✅ **ACID Transactions**: Guaranteed transactional consistency
- ✅ **Interactive Dashboard**: Real-time visualization with metrics and charts
- ✅ **Automated Workflows**: Scheduled or manual execution via Databricks Jobs

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
│  • Schema: bitcoin_data                                     │
│  • Table: bitcoin_data                                      │
│  • Volume: raw_files (JSON/Parquet)                         │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│              SQL Analytics Layer                            │
│  • Real-time Queries                                        │
│  • Historical Analysis                                      │
│  • Dashboard Integration                                    │
└────────────────────────┬────────────────────────────────────┘
                         │
                         ▼
┌─────────────────────────────────────────────────────────────┐
│              Interactive Dashboard                          │
│  • Last Price (BRL)                                         │
│  • Max Price (Historical)                                   │
│  • Min Price (Historical)                                   │
│  • Price Evolution Chart                                    │
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

4. **Analytics & Dashboard**
   - Direct SQL queries on Delta Tables
   - Integration with BI tools
   - Real-time interactive dashboards

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

**a) Bitcoin Data (Coinbase API)**
- Source: `https://api.coinbase.com/v2/prices/spot`
- Extracted Data:
  - `amount`: Current Bitcoin price in USD
  - `base`: Cryptocurrency (BTC)
  - `currency`: Reference currency (USD)
- Format: JSON
- Frequency: Real-time (on-demand)

**b) USD-BRL Exchange Rate (CurrencyFreaks API)**
- Source: `https://api.currencyfreaks.com/v2.0/rates/latest`
- Extracted Data:
  - `rates.BRL`: USD to BRL conversion rate
  - `date`: Exchange rate date/time
  - `base`: Base currency (USD)
- Format: JSON
- Authentication: API Key (via pipeline parameters)
- Frequency: Real-time (on-demand)

**Extraction Functions:**

```python
def extrair_dados_bitcoin():
    """Extracts complete JSON from Coinbase API."""
    url = 'https://api.coinbase.com/v2/prices/spot'
    resposta = requests.get(url)
    return resposta.json()

def extrair_cotacao_usd_brl():
    """Extracts USD-BRL exchange rate from CurrencyFreaks API."""
    api_key = dbutils.widgets.get("api_key")
    url = f'https://api.currencyfreaks.com/v2.0/rates/latest?apikey={api_key}'
    resposta = requests.get(url)
    return resposta.json()
```

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

**Transformation Function:**

```python
def tratar_dados_bitcoin(dados_json, taxa_usd_brl):
    """Transforms raw API data, renames columns, 
    adds timestamp and converts to BRL."""
    valor_usd = float(dados_json['data']['amount'])
    criptomoeda = dados_json['data']['base']
    moeda_original = dados_json['data']['currency']
    
    # Converting from USD to BRL
    valor_brl = valor_usd * taxa_usd_brl
    
    # Adding timestamp as datetime object
    timestamp = datetime.now()
    
    dados_tratados = [{
        "valor_usd": valor_usd,
        "valor_brl": valor_brl,
        "criptomoeda": criptomoeda,
        "moeda_original": moeda_original,
        "taxa_conversao_usd_brl": taxa_usd_brl,
        "timestamp": timestamp
    }]
    
    return dados_tratados
```

### 3️⃣ Load (Loading)

**Storage Destination:**

**Delta Table in Unity Catalog**
- Catalog: `pipeline_api_bitcoin`
- Schema: `bitcoin_data`
- Table: `bitcoin_data`
- Full Path: `pipeline_api_bitcoin.bitcoin_data.bitcoin_data`

**Storage Characteristics:**
- Format: Delta Lake
  - ACID transactions
  - Time Travel (access to historical versions)
  - Automatic Schema Evolution
  - Automatic optimizations
- Write Mode:
  - `append`: Adds new records without overwriting
  - `mergeSchema`: Allows automatic schema evolution
- Structure:
  - Table created automatically by `saveAsTable()`
  - Schema inferred from PySpark DataFrame
  - Timestamp as TIMESTAMP type (not string)

**Load Code:**

```python
# Create Spark DataFrame
df = spark.createDataFrame(dados_bitcoin_tratado)

# Delta table path in Unity Catalog
delta_table_path = "pipeline_api_bitcoin.bitcoin_data.bitcoin_data"

# Save as Delta Table (append mode)
df.write \
    .format("delta") \
    .mode("append") \
    .option("mergeSchema", "true") \
    .saveAsTable(delta_table_path)
```

**Features:**
- ✅ Incremental append for complete history
- ✅ Schema evolution enabled
- ✅ ACID transactions guaranteed
- ✅ Time travel available

---

## 📊 Data Model

### Delta Table Schema: `bitcoin_data`

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
  "valor_brl": 236125.48,
  "criptomoeda": "BTC",
  "moeda_original": "USD",
  "taxa_conversao_usd_brl": 5.4567,
  "timestamp": "2025-01-16T14:30:00"
}
```

### Example Generated Data

| valor_usd | valor_brl | criptomoeda | moeda_original | taxa_conversao_usd_brl | timestamp |
|-----------|-----------|-------------|----------------|------------------------|-----------|
| 43250.50 | 236125.48 | BTC | USD | 5.4567 | 2025-01-16 14:30:00 |
| 43280.25 | 236245.12 | BTC | USD | 5.4572 | 2025-01-16 14:31:00 |
| 43295.00 | 236310.15 | BTC | USD | 5.4575 | 2025-01-16 14:32:00 |

---

## 🛠️ Prerequisites

Before getting started, make sure you have:

- ✅ **Basic Programming Knowledge**: Any programming language
- ✅ **Internet Access**: Required for API calls and Databricks
- ✅ **Databricks Workspace**: Free account available (we'll create during the workshop)
- ✅ **CurrencyFreaks API Key**: Get it at [currencyfreaks.com](https://currencyfreaks.com)
- ✅ **Python 3.8+**: Compatible Python version
- ✅ **Python Libraries**:
  - `requests` - For HTTP requests
  - `pyspark` - For distributed processing (available in Databricks)
  - `datetime` - For timestamp manipulation
- ✅ **Willingness to Learn!** 🚀

---

## 🚀 Installation and Setup

### 1. Clone the Repository

```bash
git clone <repository-url>
cd ETL_Bitcoin
```

### 2. Configure Databricks

1. Access your Databricks workspace
2. Go to **Workspace** → **Import**
3. Select the `.py` files from the `src/` folder
4. Attach the notebook to a Databricks cluster

### 3. Configure APIs

#### CurrencyFreaks API Key

⚠️ **Important**: Never hardcode API keys in code!

**Option 1: Use Databricks Widgets (Recommended for Workflows)**
```python
# In workflow, configure Key-Value parameter:
# Key: api_key
# Value: your_api_key_here

# In code:
api_key = dbutils.widgets.get("api_key")
```

**Option 2: Use Databricks Secrets (Recommended for Production)**
```python
# In Databricks, configure the secret:
# Databricks CLI: databricks secrets create-scope --scope bitcoin-pipeline
# databricks secrets put --scope bitcoin-pipeline --key currencyfreaks-api-key

# In code:
api_key = dbutils.secrets.get(scope="bitcoin-pipeline", key="currencyfreaks-api-key")
```

**Option 3: Environment Variables**
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
CREATE SCHEMA IF NOT EXISTS pipeline_api_bitcoin.bitcoin_data
COMMENT 'Schema to store processed Bitcoin data';

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

1. Open the notebook `src/get_bitcoin_full.py` in Databricks
2. Execute all cells sequentially
3. Data will be extracted, transformed, and loaded automatically

### Workflow Execution (Recommended)

1. **Create Job in Databricks**:
   - Go to **Workflows** → **Create Job**
   - Add the notebook `get_bitcoin_macro.py` as a task
   - Configure Key-Value parameters:
     - Key: `api_key`
     - Value: `your_api_key_here`

2. **Configure Cluster**:
   - Select an existing cluster or create a new one
   - Recommended: Single Node or Small cluster for testing

3. **Configure Schedule** (Optional):
   - Set up a cron schedule (e.g., `0 */1 * * *` to run every hour)
   - Or execute manually when needed

4. **Monitor Executions**:
   - Track logs and metrics in the Databricks interface
   - Set up alerts for failures

### Main Code Example

```python
# 1. Extract data
dados_bitcoin = extrair_dados_bitcoin()
dados_cotacao = extrair_cotacao_usd_brl()

# 2. Extract conversion rate
taxa_usd_brl = float(dados_cotacao['rates']['BRL'])

# 3. Transform data
dados_bitcoin_tratado = tratar_dados_bitcoin(dados_bitcoin, taxa_usd_brl)

# 4. Create Spark DataFrame
df = spark.createDataFrame(dados_bitcoin_tratado)

# 5. Save as Delta Table
delta_table_path = "pipeline_api_bitcoin.bitcoin_data.bitcoin_data"
df.write \
    .format("delta") \
    .mode("append") \
    .option("mergeSchema", "true") \
    .saveAsTable(delta_table_path)
```

### Verify Data

After execution, data will be available in:

```sql
SELECT * FROM pipeline_api_bitcoin.bitcoin_data.bitcoin_data
ORDER BY timestamp DESC
LIMIT 10;
```

---

## 📈 Dashboard Queries

The dashboard uses 4 SQL queries to display different visualizations of Bitcoin data. All queries consult the Delta table `pipeline_api_bitcoin.bitcoin_data.bitcoin_data`.

### 1. LAST PRICE — Latest Recorded Price

Returns the most recent Bitcoin price and collection timestamp.

```sql
SELECT
  valor_brl        AS last_price,
  timestamp        AS last_timestamp
FROM pipeline_api_bitcoin.bitcoin_data.bitcoin_data
WHERE criptomoeda = 'BTC'
ORDER BY timestamp DESC
LIMIT 1
```

**Dashboard Usage**: Displayed as main value in BRL (card or metric).

### 2. MAX PRICE — Historical Maximum Price

Returns the highest price ever recorded and when it occurred.

```sql
SELECT
  valor_brl  AS max_price,
  timestamp  AS max_timestamp
FROM pipeline_api_bitcoin.bitcoin_data.bitcoin_data
WHERE criptomoeda = 'BTC'
ORDER BY valor_brl DESC, timestamp DESC
LIMIT 1
```

**Dashboard Usage**: Displayed as historical maximum metric in BRL.

### 3. MIN PRICE — Historical Minimum Price

Returns the lowest price ever recorded and when it occurred.

```sql
SELECT
  valor_brl  AS min_price,
  timestamp  AS min_timestamp
FROM pipeline_api_bitcoin.bitcoin_data.bitcoin_data
WHERE criptomoeda = 'BTC'
ORDER BY valor_brl ASC, timestamp DESC
LIMIT 1
```

**Dashboard Usage**: Displayed as historical minimum metric in BRL.

### 4. PRICE HISTORY — Line Chart

Returns complete price history ordered by timestamp for chart visualization.

```sql
SELECT
  timestamp,
  valor_usd,
  valor_brl,
  taxa_conversao_usd_brl
FROM pipeline_api_bitcoin.bitcoin_data.bitcoin_data
WHERE criptomoeda = 'BTC'
ORDER BY timestamp ASC
```

**Dashboard Usage**: Displayed as line chart showing price evolution over time.

**Possible Variations:**

- **Last N hours**: `WHERE timestamp >= CURRENT_TIMESTAMP - INTERVAL '24' HOUR`
- **Last N records**: `ORDER BY timestamp DESC LIMIT 100`
- **Hourly aggregation**: `GROUP BY DATE_TRUNC('hour', timestamp)`

### Query Summary

| Query | Ordering | Limit | Usage |
|-------|----------|-------|-------|
| LAST PRICE | `ORDER BY timestamp DESC` | `LIMIT 1` | Card/Main metric (BRL) |
| MAX PRICE | `ORDER BY valor_brl DESC` | `LIMIT 1` | Maximum metric (BRL) |
| MIN PRICE | `ORDER BY valor_brl ASC` | `LIMIT 1` | Minimum metric (BRL) |
| HISTORY | `ORDER BY timestamp ASC` | No limit | Line chart |

All queries use:
- `WHERE criptomoeda = 'BTC'` (filter)
- `AS` (alias to facilitate dashboard usage)

---

## ⚙️ Jobs & Pipelines - Orchestration

To automate the execution of our ETL pipeline, we create a Job in Databricks that orchestrates the execution of the `get_bitcoin_macro.py` script.

### What are Jobs & Pipelines?

Jobs are scheduled or manually triggered tasks in Databricks that execute notebooks or Python scripts. They allow:

- ✅ **Automation**: Execute the pipeline at regular intervals (every hour, day, etc.)
- ✅ **Orchestration**: Coordinate multiple tasks in sequence
- ✅ **Monitoring**: Track executions, logs, and history
- ✅ **Parameters**: Pass dynamic configurations (like API keys) via Key-Value pairs
- ✅ **Alerts**: Notifications in case of failure or success

### Pipeline Configuration

The pipeline is configured with:

- **Main Task**: Executes the `get_bitcoin_macro.py` notebook
- **Key-Value Parameters**:
  - `api_key`: CurrencyFreaks API key for currency conversion
- **Cluster**: Databricks cluster for processing
- **Schedule** (optional): Automatic scheduling for periodic collection

### Pipeline Structure

```
📝 Task: get_bitcoin_macro - Executes extraction and load script
🔑 Parameters: API key configuration via Key-Value
⚙️ Cluster: Execution environment
📊 Output: Data saved in Delta Table pipeline_api_bitcoin.bitcoin_data.bitcoin_data
```

---

## 📊 Dashboard Visualization

After collecting data, we create an interactive Dashboard in Databricks to visualize and monitor Bitcoin prices in real-time.

### What is a Dashboard?

A Dashboard is a visual interface that displays metrics, charts, and analyses of collected data. It allows:

- ✅ **Real-time Visualization**: See the latest collected prices
- ✅ **Main Metrics**: Latest price, historical maximum, historical minimum
- ✅ **Temporal Charts**: Price evolution over time
- ✅ **Quick Analysis**: Identify trends and patterns
- ✅ **Sharing**: Share insights with stakeholders

### Dashboard Components

The dashboard uses 4 SQL queries to display different visualizations:

1. **LAST PRICE**: Latest price in BRL collected
2. **MAX PRICE**: Highest historical price in BRL
3. **MIN PRICE**: Lowest historical price in BRL
4. **HISTORY**: Line chart with temporal evolution

### Dashboard Elements

- 📈 **Metric Cards**: Latest price, maximum and minimum
- 📊 **Line Chart**: Price evolution over time
- 🔄 **Automatic Update**: Data updated as the pipeline executes
- 💰 **Values in BRL**: All values displayed in Brazilian Real

### How to Create the Dashboard

1. Access **SQL → Dashboards** in Databricks
2. Create a new dashboard
3. Add visualizations using the documented SQL queries
4. Configure automatic refresh
5. Share with your team

---

## 🔐 Security and Best Practices

### Security

- ✅ **API Keys never hardcoded**: Always use Databricks Secrets, Widgets, or environment variables
- ✅ **Parameterized secrets in workflows**: Secure credential configuration via Key-Value pairs
- ✅ **Data governance via Unity Catalog**: Centralized access control
- ✅ **ACID-compliant storage**: Guaranteed transactional consistency
- ✅ **Time travel for auditing**: Complete change traceability

### Data Governance

- ✅ Use Unity Catalog for hierarchical organization
- ✅ Define clear and descriptive schemas
- ✅ Document tables and columns
- ✅ Configure data retention policies

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
├── README.md                     # Main documentation
│
├── img/
│   └── SeUZPWKQ.png              # Project cover image
│
└── src/
    ├── get_bitcoin_full.py       # Complete notebook with documentation
    ├── get_bitcoin_macro.py      # Script for workflows (simplified)
    ├── aquecimento_python.py     # Python basics tutorial
    └── aquecimento_sql.py        # SQL basics tutorial
```

### Main Files

- **`get_bitcoin_full.py`**: Complete notebook with detailed explanations, examples of saving in JSON/CSV/Parquet/Delta, and visualizations
- **`get_bitcoin_macro.py`**: Simplified version for use in workflows, only saves to Delta Table
- **`aquecimento_python.py`**: Python basics tutorial (variables, print, methods)
- **`aquecimento_sql.py`**: SQL basics tutorial (SELECT, WHERE, ORDER BY, LIMIT)

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

### Why Use Databricks and PySpark?

#### PySpark vs Pandas

| Characteristic | Pandas | PySpark |
|----------------|--------|---------|
| Scalability | Single machine (RAM limited) | Distributed (clusters) |
| Data Volume | Megabytes to Gigabytes | Terabytes to Petabytes |
| Processing | In-memory (RAM) | Distributed (disk + memory) |
| Use Case | Exploratory analysis, small datasets | Big Data, production pipelines |

**In this project**: We use PySpark because:
- ✅ Prepared to scale
- ✅ Native integration with Databricks
- ✅ Delta Lake support
- ✅ Distributed processing

#### Delta Lake vs Simple Parquet

| Characteristic | Parquet | Delta Lake |
|----------------|---------|------------|
| ACID Transactions | ❌ | ✅ |
| Time Travel | ❌ | ✅ |
| Schema Evolution | Manual | Automatic |
| Updates/Deletes | ❌ | ✅ |
| Performance | Good | Optimized |

**In this project**: We use Delta Lake because:
- ✅ Complete price history (Time Travel)
- ✅ Consistency guarantees (ACID)
- ✅ Allows schema evolution without breaking old data
- ✅ Automatic optimizations

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
- ✅ **Dashboard Creation**: Interactive data visualization
- ✅ **Best Practices**: Security, versioning, and documentation

---


