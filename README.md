# ETL Pipeline (CSV → PostgreSQL)

This project implements an end-to-end ETL (Extract, Transform, Load) pipeline using Python.  
The pipeline extracts data from a CSV file, transforms it using Pandas, and loads the cleaned data into a PostgreSQL database.

---

## Project Structure

```
etl-csv-postgres/
│
├── data/
│   └── sales.csv
├── etl.py
├── config.py
├── requirements.txt
└── README.md
```

---

## ETL Workflow

### Extract
- Read CSV file using Pandas
- Load data into DataFrame

### Transform
- Remove duplicate records
- Handle missing values
- Convert date column to datetime format
- Create new column `amount_with_tax`

### Load
- Connect to PostgreSQL database
- Create table if not exists
- Load transformed data into `sales` table

---

## Technologies Used

- Python  
- Pandas  
- PostgreSQL  
- SQLAlchemy  
- psycopg2  

---

## Setup Instructions

### 1. Install Dependencies
```
pip install -r requirements.txt
```

### 2. Configure Database
Update `config.py` with your PostgreSQL credentials:

```python
DB_CONFIG = {
    "user": "postgres",
    "password": "your_password",
    "host": "localhost",
    "port": "5432",
    "database": "etl_project"
}
```

### 3. Run ETL Pipeline
```
python etl.py
```

---

## Sample Output

| order_id | customer | amount | date | amount_with_tax |
|----------|----------|--------|------|-----------------|
| 1 | Sushma | 500 | 2024-01-01 | 590 |
| 2 | Ravi | 700 | 2024-01-02 | 826 |
| 3 | Anil | 450 | 2024-01-03 | 531 |

---

## Features

- End-to-end ETL pipeline  
- CSV to PostgreSQL data loading  
- Data cleaning and transformation  
- Automated table ingestion  
- Reusable Python script  

---

## Author

Sushma Anumalla
