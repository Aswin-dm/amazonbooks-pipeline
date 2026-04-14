Amazon Books ETL Pipeline
This project is an end-to-end Data Engineering pipeline designed to extract book data from Amazon, transform it for analysis, and load it into a structured database. It leverages Apache Airflow for orchestration and PostgreSQL as the data warehouse.
 
📌 Project Overview
The pipeline automates the process of gathering information about books (e.g., Data Engineering, Self-Improvement, or Best Sellers) from Amazon. This data is cleaned and stored systematically to enable further analysis, such as price tracking or popularity trends. 

🛠 Tech Stack
Language: Python 3.x

Orchestration: Apache Airflow

Database: PostgreSQL / PGAdmin

Libraries: BeautifulSoup4 (Scraping), Pandas (Transformation), Requests

Containerization: Docker & Docker Compose

```
amazonbooks-pipeline/
├── dags/
│   └── amazon_books_dag.py
├── scripts/
│   └── extract_books.py
├── docker-compose.yaml
├── requirements.txt
└── README.md
```
🚀 Getting Started
1. Prerequisites
Ensure you have the following installed:

Docker Desktop

Python 3.9+

2. Installation
Clone the repository:

Bash
git clone https://github.com/Aswin-dm/amazonbooks-pipeline.git
cd amazonbooks-pipeline
3. Setup Environment
Create a virtual environment and install dependencies:

Bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
4. Running with Docker
Start the Airflow and Postgres containers:

Bash
docker-compose up -d
5. Accessing the Pipeline
Airflow UI: http://localhost:8080 (Default login: airflow/airflow)

PGAdmin: http://localhost:5050 (To view the stored book data)

⚙️ How it Works
Extract: The pipeline sends requests to Amazon search result pages and parses the HTML using BeautifulSoup to find book titles, authors, prices, and ratings.

Transform: Data is cleaned (handling missing prices, stripping whitespace) and converted into a structured Pandas DataFrame.

Load: The cleaned data is inserted into a PostgreSQL table using the PostgresOperator or PythonOperator.

⚠️ Disclaimer
This project is for educational purposes. Web scraping Amazon is subject to their Terms of Service. Always use headers and respect robots.txt policies.
