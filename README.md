# Azure End-to-End Data Engineering Project

## Project Overview
This project demonstrates an end-to-end data engineering solution using Microsoft Azure for the entire ETL (Extract, Transform, Load) process. The pipeline leverages various Azure services for data ingestion, transformation, and reporting. The dataset used for this project is sourced from the NYC Taxi and Limousine Commission Trip Record Data.

## Architecture
![Architecture](https://github.com/user-attachments/assets/87736063-c566-4cc4-97c6-22049170b603)


The architecture comprises the following stages:
1. **Ingestion**
   - Data is ingested using Azure Data Factory (ADF) pipelines.
   - Data is fetched via API from the NYC Taxi and Limousine Commission [Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page).
   - ADF pipelines include:
     - **Copy Data Pipeline**: Copies data from the source API to a storage location.
     - **For Each Pipeline**: Handles month-wise data extraction for the entire year (1-12 months).
   - Data is stored in Parquet format in Azure Data Lake Gen2 for efficient handling and compatibility.

2. **Transformation**
   - Data transformation is performed using Databricks.
   - A layered storage structure is used:
     - **Bronze Layer**: Stores raw data in Azure Data Lake Gen2.
     - **Silver Layer**: Holds transformed data for intermediate processing.
     - **Gold Layer**: Contains final transformed data stored in Delta Lake format for optimized querying and analytics.
   - Transformation scripts:
     - PySpark scripts
     - SQL queries executed within Databricks notebooks.

3. **Reporting**
   - Transformed data is connected to Power BI for visualization and reporting.
   - The Delta Lake format enables high-performance analytics.

## Tools and Technologies
- **Ingestion**: Azure Data Factory (ADF)
- **Storage**: Azure Data Lake Gen2 (Bronze, Silver, Gold containers)
- **Transformation**: Databricks (PySpark and SQL scripts)
- **Reporting**: Power BI
- **File Format**: Parquet for raw and intermediate data, Delta for final data

## Source Data
- Dataset: [NYC Taxi and Limousine Commission Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

## Key Features
- Automated data extraction using Azure Data Factory.
- API-based data ingestion for monthly trip records.
- Efficient and scalable storage using Azure Data Lake Gen2.
- Layered architecture for data processing (Bronze, Silver, Gold containers).
- High-performance data transformation with Databricks.
- Interactive and insightful reporting using Power BI.

## Steps to Reproduce
1. Set up Azure Data Factory and configure pipelines for API-based data ingestion.
2. Store raw data in Azure Data Lake Gen2 Bronze container in Parquet format.
3. Use Databricks for data transformation:
   - Clean and process raw data from Bronze to Silver.
   - Perform aggregations and final transformations from Silver to Gold.
   - Store final data in Delta format.
4. Connect the Gold container to Power BI for reporting and visualization.

## Data Architecture
The project follows a structured data architecture:
- **Bronze Layer**: Raw data storage.
- **Silver Layer**: Processed and partially transformed data.
- **Gold Layer**: Fully transformed, analytics-ready data in Delta format.

## Future Enhancements
- Incorporate real-time data processing.
- Enhance reporting dashboards with advanced analytics.
- Explore additional Azure services for improved scalability and performance.
