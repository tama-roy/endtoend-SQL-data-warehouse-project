# End-to-end-SQL-data-warehouse-project
I completed a full end-to-end data engineering project where the objective was to design and implement a SQL-based data warehouse from scratch, following industry-standard architecture and data engineering principles.

The project was structured to replicate how production analytics data pipelines are typically built, but at a controlled, project scale.

# Project Objective
The core problem addressed was:
How do we reliably convert raw, unstructured or semi-structured source data into clean, trusted, analytics-ready datasets that can be used by business users for reporting and decision-making?

To solve this, I implemented a layered data warehouse architecture with a well-defined ETL pipeline, ensuring:
1. Data traceability
2. Data quality
3. Scalability
4. Clear separation between raw data and business logic

# Data Architecture
The data architecture for this project follows Medallion Architecture Bronze, Silver, and Gold layers:
1. Bronze Layer: Stores raw data as-is from the source systems. Data is ingested from CSV Files into SQL Server Database.
2. Silver Layer: This layer includes data cleansing, standardization, and normalization processes to prepare data for analysis.
3. Gold Layer: Houses business-ready data modeled into a star schema required for reporting and analytics.

<img width="1156" height="606" alt="image" src="https://github.com/user-attachments/assets/b82d8380-a141-4a44-8257-14d2d5e9d076" />


# ETL Pipeline Design & Implementation
1. Extract
   - Raw data files were loaded directly into Bronze tables using SQL-based ingestion.
   - No transformations were applied during extraction.
   - Design principle: Raw data should never be altered at ingestion.

2. Transform- Transformations were implemented entirely in SQL, with clear separation between:
   a) Data quality transformations (Bronze → Silver)
   b) Business logic transformations (Silver → Gold)

3. Load
   - Cleaned and modeled data was loaded into final warehouse tables.
   - Tables could be safely rebuilt without corrupting downstream logic.
  
# Data Modeling Approach
I implemented dimensional modeling using:
- Fact tables for transactional metrics
- Dimension tables for descriptive attributes
- Proper keys (surrogate keys) to enable efficient joins
