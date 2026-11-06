# Healthcare Data Engineering Project

## Project Overview

This project demonstrates an end-to-end Healthcare Data Engineering pipeline built using **Databricks, Apache Spark, PySpark, Delta Lake, and SQL**.

The project processes synthetic healthcare data, including patients, doctors, appointments, and billing information. It follows the Medallion Architecture (Bronze, Silver, and Gold) to ingest, clean, transform, validate, and analyze healthcare data.

## Business Objective

Healthcare organizations generate data from multiple sources, such as patient registration, doctor information, appointments, and billing.

The objective of this project is to build a reliable data pipeline that:
- Ingests raw healthcare data.
- Cleans and transforms the data.
- Validates data quality.
- Generates analytics-ready datasets.
- Automates pipeline execution using Databricks Workflows.

**Note:** All data used in this project is synthetic and created for learning purposes.

## Technologies Used

- Databricks Free Edition
- Apache Spark
- PySpark
- Python
- SQL
- Delta Lake
- Git and GitHub
- Databricks Workflows (Lakeflow Jobs)

## Architecture

The project follows the Medallion Architecture.

```text
Synthetic Healthcare Data
          |
          v
     Bronze Layer
     Raw Data Ingestion
          |
          v
     Silver Layer
   Data Cleaning and
   Transformation
          |
          v
      Gold Layer
   Business Analytics
          |
          v
    SQL Analytics
          |
          v
   Reporting and Insights

   Data Quality Checks
   Validate Silver Data

   Databricks Workflow
   Orchestrates All Notebooks
```

## Project Data

The project uses four synthetic datasets:

| Dataset | Records |
|---|---:|
| Patients | 6 |
| Doctors | 5 |
| Appointments | 8 |
| Billing | 8 |

## Medallion Architecture

### 1. Bronze Layer

The Bronze layer stores raw healthcare data in Delta tables.

Tables:
- `bronze_patients`
- `bronze_doctors`
- `bronze_appointments`
- `bronze_billing`

### 2. Silver Layer

The Silver layer cleans and transforms Bronze data.

Activities:
- Data validation.
- Null and duplicate checks.
- Age group classification.
- Doctor experience classification.
- Appointment and billing validation.
- Referential integrity checks.

Tables:
- `silver_patients`
- `silver_doctors`
- `silver_appointments`
- `silver_billing`

### 3. Gold Layer

The Gold layer contains analytics-ready tables.

Tables:
- `gold_hospital_kpi`
- `gold_department_analytics`
- `gold_doctor_performance`
- `gold_billing_analytics`
- `gold_monthly_trends`
- `gold_patient_city`

## Notebook Execution Flow

| Notebook | Purpose |
|---|---|
| `00_Create_Healthcare_Data` | Generates synthetic healthcare data |
| `01_Bronze_Ingestion` | Loads raw data into Bronze tables |
| `02_Silver_Transformation` | Cleans and transforms data |
| `03_Gold_Analytics` | Creates Gold analytics tables |
| `04_Data_Quality` | Performs data quality validation |
| `05_SQL_Analytics` | Performs SQL-based analytics |

## Data Quality Results

The Data Quality notebook performs 16 validation checks.

| Metric | Result |
|---|---:|
| Total Checks | 16 |
| Passed Checks | 16 |
| Failed Checks | 0 |
| Overall Status | ALL CHECKS PASSED |

The audit results are stored in:

`workspace.healthcare.dq_audit_results`

## Workflow Orchestration

The project uses Databricks Workflows to execute all six notebooks in sequence.

Execution order:

1. Create Healthcare Data
2. Bronze Ingestion
3. Silver Transformation
4. Gold Analytics
5. Data Quality
6. SQL Analytics

All six tasks completed successfully in the workflow run.

The workflow can also be configured with a weekly scheduled trigger.

## Gold Analytics Highlights

The Gold layer provides the following hospital-level insights:

| Metric | Result |
|---|---:|
| Total Patients | 6 |
| Total Doctors | 5 |
| Total Appointments | 8 |
| Completed Appointments | 5 |
| Pending Appointments | 2 |
| Cancelled Appointments | 1 |
| Total Revenue | 11,500 |
| Pending Amount | 4,800 |

## How to Run the Project

1. Open the Healthcare-Data-Engineering repository in Databricks.
2. Open the `notebooks` folder.
3. Run `00_Create_Healthcare_Data`.
4. Run the remaining notebooks in the documented execution order.
5. Verify the Bronze, Silver, and Gold Delta tables.
6. Execute the Data Quality notebook.
7. Run the SQL Analytics notebook.
8. Alternatively, execute the complete pipeline through Databricks Workflows.

## Catalog and Schema

Catalog: `workspace`

Schema: `healthcare`

Raw data volume:

`/Volumes/workspace/healthcare/raw_data/`

## Learning Outcomes

Through this project, we practice:

- Building end-to-end data engineering pipelines.
- Working with PySpark and Spark SQL.
- Implementing Medallion Architecture.
- Creating and managing Delta tables.
- Performing data quality checks.
- Building analytical datasets.
- Orchestrating notebook execution using Databricks Workflows.
- Managing project code using GitHub.

## Future Enhancements

- Implement incremental data ingestion.
- Add automated failure notifications.
- Improve pipeline monitoring and logging.
- Create dashboards using Gold analytics tables.
- Add automated testing.
- Implement CI/CD deployment practices.

---

**Project:** Healthcare Data Engineering  
**Environment:** Databricks Free Edition  
**Data:** Synthetic healthcare datasets  
**Repository:** Healthcare-Data-Engineerings