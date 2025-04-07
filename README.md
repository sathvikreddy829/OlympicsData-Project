## OlympicsDataEngineering - Project
This project demonstrates a robust, secure, and scalable modern data platform built on Azure Data Factory, Azure Data Lake Gen2, Databricks, and Delta Live Tables, designed to ingest, transform, and serve data related to Olympic athletes, events, coaches, and countries.

🔄 Bronze Layer - Ingestion
Implemented dynamic and metadata-driven ingestion using Azure Data Factory (ADF).
Used Lookup, ForEach, and If activities with parameterized Copy Data pipelines.
Supported ingestion from both external sources (HTTP) and internal ADLS containers.
Ensured reusability, parameterization, and scalability for adding more datasets in the future.

🛡️ Security and Governance
Integrated with Unity Catalog for fine-grained access control.
Leveraged external locations to secure storage paths.
Maintained data governance and lineage tracking throughout all layers.

🧼 Silver Layer - Data Refinement
Used Databricks Notebooks with DLT to read from Bronze layer and apply:
Data type enforcement
Null handling and default value filling
Column cleanup and standardization
Spark optimizations for performance
Produced clean, typed, and analytics-ready datasets stored in the Silver zone.

🧠 Gold Layer - Curated Entities & Historical Tracking
Created Delta Live Tables (DLT) in the Gold layer for core business entities (Athletes, Coaches, Events, etc.).
Implemented SCD Type 1 logic using DLT’s apply_changes() API for capturing historical changes with minimal code.
Curated datasets support both:

Historical trend analysis

Real-time reporting and ML training
