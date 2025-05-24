# Database Insert Script: PostgreSQL & MS SQL (IndusInd Bank I4C Data)

This project provides Python and Jupyter Notebook-based scripts for inserting large `.csv` datasets into both **PostgreSQL** and **Microsoft SQL Server** databases. 


## 🧰 Features

- Chunked CSV reading using `pandas` to handle large files
- Database connections using:
  - `psycopg2` and `sqlalchemy` for **PostgreSQL**
  - `pyodbc` and `sqlalchemy` for **MS SQL Server**
- Auto conversion of columns to lowercase
- Conversion of all values to string to avoid dtype issues
- Missing values filled with 0
- Insertion using `.to_sql()` with `if_exists='append'` logic

---

## 🗂 File Description

- `2024.csv`: Source data to be inserted (stored locally, not committed to GitHub)
- `insert_to_postgres.ipynb`: Notebook to insert data into PostgreSQL under the `public.i4c_2024` table
- `insert_to_mssql.ipynb`: Notebook to insert data into MS SQL `FINCORE_BRIDGE_DB` under `i4c_2024`

---

## 🛠 Technologies Used

- **Python 3**
- **Jupyter Notebook**
- `pandas`, `numpy`
- `sqlalchemy`
- `psycopg2` (PostgreSQL)
- `pyodbc` (MS SQL Server)
- `openpyxl`, `xlsxwriter`
- `tqdm` for progress tracking

---

## 📌 Notes

-  PostgreSQL insertion requires valid IP, port, user credentials.
-  MS SQL insertion uses ODBC Driver 17 — ensure it's installed on your machine.
-  Schema is defined (`public`) for Postgres, but not for MS SQL.
-  Be careful with hardcoded credentials (replace them with env vars for production use).

---

## 🔐 Security Disclaimer

> The database credentials in the sample code (`postgres:postgres`, etc.) are for illustrative purposes only. Always secure your credentials using environment variables or secret managers in real applications.

---

## 📎 Sample Output

```bash
Postgres database connected successfully
88it [00:14,  6.08it/s]
