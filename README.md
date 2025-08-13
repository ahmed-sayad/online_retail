# Online Retail Data Engineering Pipeline with Power BI Visualization

## Overview
This project demonstrates an **end-to-end Data Engineering workflow** using the [UCI Online Retail dataset](https://archive.ics.uci.edu/dataset/352/online+retail).  
It covers **ETL** (Extract, Transform, Load) processes, secure credential management, Snowflake Data Warehouse integration, and Power BI dashboards for business insights.

## Dataset
- **Source:** UCI Machine Learning Repository
- **Period:** 01/12/2010 – 09/12/2011
- **Description:** Transactions of a UK-based online retailer, including invoices, products, quantities, customer IDs, and countries.

## Workflow

### 1. Extract
- Notebook: `1-fetch_online_dataset(extract).ipynb`
- Downloads the dataset from UCI.
- Handles missing values, data type issues, and encoding.

### 2. Transform
- Notebook: `2-create_star_schema(transform).ipynb`
- Cleans data (removes canceled orders, handles missing IDs, fixes negative quantities).
- Creates a **star schema**:
  - `FACT_SALES` – Sales transactions
  - `DIM_CUSTOMER` – Customer details
  - `DIM_PRODUCT` – Product details
  - `DIM_TIME` – Date hierarchy

### 3. Load
- Notebook: `3-load_data_to_snowflake(load 2 DWH).ipynb`
- Loads transformed data into **Snowflake** for analytics.
- Uses encrypted environment variables for security.

## Security
- Credentials stored in `.env` → encrypted into `.env.enc`.
- `secret.key` is used for AES encryption/decryption.
- Notebook `2.2-env_encrypted_credentials.ipynb` manages credentials securely.

## Visualization
**Power BI dashboards** provide:
- Top-selling products
- Revenue trends over time
- Sales by country
- Customer purchasing behavior

## Tech Stack
- **Python** – ETL processing
- **Snowflake** – Cloud data warehouse
- **Power BI** – Visualization
- **Jupyter Notebooks** – Development environment

## License
This project is released under the MIT License.
