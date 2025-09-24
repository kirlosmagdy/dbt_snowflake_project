# End-to-End Data Engineering Project with dbt, Snowflake 

## 📌 Overview
This project demonstrates a **complete data engineering pipeline** built using:
- **dbt (Data Build Tool)** for SQL-based data transformations and modeling
- **Snowflake** as the cloud data warehouse
- **Apache Airflow** for workflow orchestration and scheduling
- **Python** for automation and scripting

The pipeline covers:
1. **Data Ingestion** – loading raw data into Snowflake  
2. **Transformation** – building staging, intermediate, and mart layers with dbt  
3. **Orchestration** – scheduling and monitoring workflows using Apache Airflow  

---

## ⚙️ Tech Stack
- **dbt Core** – SQL transformations, data models, testing, and documentation  
- **Snowflake** – scalable, cloud-native data warehouse  
- **Apache Airflow** – DAG-based workflow orchestration  
- **Python** – scripting and automation logic  
- **Git/GitHub** – version control and collaboration  

---

## 📂 Project Structure
snowflake_data_project/
│── models/ # dbt models (staging, marts, transformations)
│── dags/ # Airflow DAGs for scheduling workflows
│── logs/ # Airflow logs
│── seeds/ # Sample seed data for dbt
│── macros/ # Custom dbt macros
│── dbt_project.yml # Main dbt configuration file
│── README.md # Documentation



---

## 🚀 Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/kirlosmagdy/dbt_snowflake_project.git
cd dbt_snowflake_project
```

### 2. Set Up Virtual Environment

```bash
python -m venv venv        # Activate venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
```

### 3. Configure dbt Connection to Snowflake

Update the profiles.yml file in ~/.dbt/ with your Snowflake credentials:

snowflake_project:
  outputs:
    dev:
      type: snowflake
      account: your_snowflake_account
      database: finance_db
      user: dbt_user
      password: your_password
      warehouse: finance_wh
      role: ACCOUNTADMIN
      schema: raw
  target: dev


### 4. Run dbt Models

```bash
dbt run        # Build models
dbt test       # Run tests to validate data integrity
```

## 📊 Data Flow

1- Raw data ingestion → Snowflake raw schema
2- Staging models → Cleaned and structured layer in Snowflake
3- Marts layer → Business-focused tables for analytics and reporting
