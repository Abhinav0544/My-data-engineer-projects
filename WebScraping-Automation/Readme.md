# 📰 Adverse Media Scraping Project

This project automates the scraping, processing, and storage of adverse media news articles. It fetches news using a Google News RSS feed, processes and cleans the data, assigns unique identifiers (ARNs), removes duplicates, and stores the final dataset in a SQLite database. It also exports the data to Excel for downstream reporting or analysis.

---

## 📂 Project Structure

adverse_media_scraping_project/
│
├── db2.sqlite # SQLite database to store articles
├── news_articles_<date>to<date>.xlsx # Output Excel file
├── test_news.csv # CSV containing articles to deduplicate
├── chromedriver.exe # Chrome WebDriver for scraping
└── script.py # Python script for scraping and processing

yaml
Copy
Edit

---

## 🚀 Features

- Scrapes full article content from Google News RSS links using Selenium and BeautifulSoup.
- Converts and cleans columns: standardizes column names, ensures data type consistency.
- Assigns unique ARN (Article Reference Number) starting from the max existing ARN in the database.
- Handles empty database gracefully by starting ARN numbering from zero.
- Drops duplicates between month-end and beginning to prevent redundant data.
- Exports to Excel for review and storage.
- Appends processed articles to a persistent SQLite database.

---

## 🛠️ Tech Stack

- **Python 3**
- **Pandas** – DataFrame manipulation
- **Selenium + BeautifulSoup** – Web scraping
- **SQLite3** – Lightweight database
- **Excel Export** – via Pandas
- **JSON** – Handling structured article metadata

---

## 🧾 Requirements

- Python 3.7+
- Google Chrome installed
- ChromeDriver installed and path updated

### Install required Python packages:

```bash
pip install pandas selenium beautifulsoup4 openpyxl
⚙️ Configuration
Set WebDriver path:
Update webdriver_path in the script with your local ChromeDriver path.

Database path:
Ensure the SQLite path is correctly configured to where db2.sqlite resides.

CSV input file:
Ensure test_news.csv is placed correctly and readable.

🧪 How It Works
Step-by-step Overview:
Rename and clean column names in the DataFrame.

Connect to db2.sqlite and fetch the maximum arnno.

Create unique ARNs for current rows and format them as 'ARN####'.

Export a cleaned Excel file with a date-based filename.

Ensure type consistency for all relevant columns.

Append new rows into article2 table in the SQLite database.

Remove duplicates using test_news.csv.

(Optional) Use Selenium + BeautifulSoup to fetch full article body content using the article link (demonstrated on a sample).

📝 Notes
This script assumes article links are accessible and well-formed.

Basic error handling is implemented during scraping.

Article body is extracted from JSON-LD script if available.

🧼 To-Do / Future Enhancements
Implement full deduplication logic using article text, title, and timestamp similarity.

Move configuration (paths, filenames) to .env or a config file.

Add logging and improved exception handling.

Schedule script execution via Task Scheduler or cron.

Enable parallel scraping for better performance.

📅 Naming Convention
Final Excel export is saved as:
news_articles_<start_date>_to_<end_date>.xlsx

👤 Author
Abhinav Jaikumar Kallooramana
Data Scientist @ LTIMindtree
[GitHub Portfolio coming soon]
