ZaubaCorp Past Director Scraper
This Python script automates the extraction of past director details from ZaubaCorp using Selenium with undetected ChromeDriver to bypass Cloudflare protection. Extracted data is stored in a Microsoft SQL Server database.

Features
Auto-installs compatible ChromeDriver

Bypasses Cloudflare bot protection

Solves simple math CAPTCHAs

Scrapes and stores director details from company pages

Handles large datasets in chunks

Logs errors and processing information

Requirements
bash
Copy
Edit
pip install -r requirements.txt
Key libraries:

undetected-chromedriver

chromedriver-autoinstaller

selenium

sqlalchemy

pandas

Database
Ensure your SQL Server credentials and connection string are correctly set in the script:

python
Copy
Edit
engine = create_engine('mssql+pyodbc://<username>:<password>@<host>:<port>/<dbname>?driver=ODBC+Driver+17+for+SQL+Server')
Usage
Run the script:

bash
Copy
Edit
python your_script_name.py
Ensure df['Website'] is defined (e.g., loaded from a CSV with company URLs).

Logs
Runtime logs: cloudflare_bypass.log

Errors: error_log.txt
