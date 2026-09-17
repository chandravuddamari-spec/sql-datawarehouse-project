# SQL Data Warehouse

A modern data warehouse built on SQL Server Express using the Bronze, Silver, and Gold layers to ingest, cleanse, model, and report on sales data.

## Project Overview

This repository demonstrates how to design and implement a SQL Architecture data warehouse:

<img width="1155" alt="image" src="https://github.com/user-attachments/assets/05540939-663b-47e6-9666-1471211c4c40" />

- Bronze Layer: Stores raw CSV extracts as-is from source systems (ERP and CRM).
- Silver Layer: Cleanses, standardizes, and normalizes data for consistency.
- Gold Layer: Builds a star schema (fact and dimension tables) optimized for analytics and reporting.

The project includes:

- ETL Pipelines: SQL scripts (and optional Python loaders) to move data through each layer.
- Data Modeling: Star schema creation optimized for analytical queries.
- Analytics and Reporting: Sample SQL-based reports and dashboards.
- Documentation: Architecture diagrams, data dictionaries, and design notes.

## Repository Structure

```
|-- .github/workflows/ci.yml    # (optional) CI: SQL linting and smoke tests
|-- data
|   |-- bronze/raw_csvs         # Raw source CSV files
|   |-- silver/cleansed         # Cleaned/parquet outputs
|   +-- gold/star_schema        # Final table exports (CSV or parquet)
|-- docs
|   |-- architecture.md         # Medallion architecture details
|   |-- data_dictionary.md      # Field definitions and sources
|   +-- diagrams/               # DrawIO files and exports
|-- etl
|   |-- bronze_load.sql         # Ingest raw CSV -> staging tables
|   |-- silver_transform.sql    # Cleansing and normalization
|   +-- gold_model.sql          # Star schema creation
|-- src                         # (optional) Python/Spark ETL code
|   |-- bronze_loader.py
|   |-- silver_cleaner.py
|   +-- gold_builder.py
|-- notebooks/exploration.ipynb # Exploratory data analysis examples
|-- dashboards/                 # BI artifacts (PowerBI, Tableau files)
|-- CHANGELOG.md                # Changelog following Keep a Changelog
|-- CONTRIBUTING.md             # Contribution guidelines
|-- LICENSE                     # Project license (e.g., MIT)
|-- README.md                   # This file
+-- requirements.txt            # Python dependencies (if any)
```

## Prerequisites

- SQL Server Express (or Developer Edition)
- SQL Server Management Studio (SSMS)
- Git to clone the repository
- Python 3.8+ (if using Python loaders)

## Setup and Installation

1. Clone the repo
   ```bash
   git clone https://github.com/saichandravuddamari/sql-data-warehouse.git
   cd sql-data-warehouse
   ```
2. Prepare data
   - Place your raw CSVs in data/bronze/raw_csvs/.
3. Run Bronze ETL
   - Open etl/bronze_load.sql in SSMS and execute to load staging tables.
4. Run Silver ETL
   - Execute etl/silver_transform.sql to cleanse and populate Silver tables.
5. Run Gold ETL
   - Execute etl/gold_model.sql to build the star schema in Gold.

Optional: If you prefer Python scripts, install dependencies:
```bash
pip install -r requirements.txt
```
Then run:
```bash
python src/bronze_loader.py
python src/silver_cleaner.py
python src/gold_builder.py
```

## Analytics and Reporting

- Sample reports and dashboards are located in dashboards/.
- Use provided SQL queries or BI tool files (PowerBI, Tableau) to visualize:
  - Customer behavior
  - Product performance
  - Sales trends

## Contributing

We welcome contributions! Please read CONTRIBUTING.md for details on:

- Opening issues
- Submitting pull requests
- Coding and documentation standards

## Changelog

See CHANGELOG.md for a history of changes and releases.

## License

This project is licensed under the MIT License.

## Maintainer

Sai Chandra Vuddamari
Research and Innovation Analyst

I am a detail-oriented analyst who builds structure out of critical thinking, analyzing data through Excel trackers, dashboards, and SQL/R. With over 4 years of professional experience, I work directly with stakeholders to close gaps and maintain accurate reporting in fast-paced, evolving environments.

Key Skills: SQL, Python, R, VBA

Contact:
- Email: sssaichandra375@gmail.com
- GitHub: https://github.com/saichandravuddamari
- LinkedIn: https://www.linkedin.com/in/saichandravuddamari

## Credits

`datasets/source_crm/sales_details.csv` restored from [DataWithBaraa/sql-data-warehouse-project](https://github.com/DataWithBaraa/sql-data-warehouse-project) by Baraa Khatib Salkini (MIT License).
