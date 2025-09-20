## Disaster Response – Insurance Operations

### Project Overview

This project is focused on building a data engineering pipeline to process disaster-related insurance claims and response operations. It leverages PostgreSQL, Airflow (via Astronomer), and Docker to create an end-to-end environment for:

- Ingesting disaster response data.

- Transforming and cleaning insurance claims data.

- Orchestrating workflows with Airflow.

- Preparing structured outputs for analytics and reporting.

### Data Architecture

![Data Architecture](https://github.com/adetonayusuf/disaster_insurance/blob/main/Disaster%20Data%20Architecture.gif)

### Tech Stack

- Python 3.10+ (Virtual Environment recommended)

- PostgreSQL (relational database)

- Docker & Docker Compose (containerization)

- Astronomer (Astro CLI) (Airflow orchestration)

### Project Structure
Disaster Response - Insurance Operations/
│── Desaster Response/               # Main project folder
│   ├── dags/                        # Airflow DAGs
│   ├── plugins/                     # Custom operators & hooks
│   ├── Dockerfile                   # Image definition for Airflow
│   ├── requirements.txt             # Python dependencies
│   ├── .env                         # Environment variables (not in repo)
│   └── docker-compose.override.yml  # Local service overrides
│
└── README.md                        # Project documentation

### Setup & Installation
#### 1  Clone the repository
git clone https://github.com/<your-username>/disaster-response.git
cd "Disaster Response - Insurance Operations/Desaster Response"

#### 2 Create and activate a virtual environment (optional but recommended)
python -m venv venv
venv\Scripts\activate      # On Windows
source venv/bin/activate   # On Mac/Linux

#### 3 Install dependencies
pip install -r requirements.txt

#### 4 Ensure Docker Desktop is running

Check if Docker is up:

docker ps

#### 5 Create .env file

Add your environment variables inside a .env file:

POSTGRES_USER=airflow
POSTGRES_PASSWORD=airflow
POSTGRES_DB=disasterdb
AIRFLOW_UID=50000

#### 6 Start Airflow locally with Astronomer
astro dev start


This will:

Build the Airflow image.

Start webserver, scheduler, Postgres, and other services.

#### 7 Access Airflow UI

Open: http://localhost:8080

Default login:

Username: airflow

Password: airflow

### Usage

- Place raw disaster/insurance claim data into the data/ folder (or connect via API/DB).

- Define workflows inside dags/.

- Trigger DAGs in Airflow UI to:

    - Extract data into Postgres.

    - Transform and clean missing values (e.g., state, obligateddate, damadcategory).

    - Load clean datasets into analytics-ready tables.

### Testing

Run inside the project folder:

astro dev run pytest

### Future Improvements

Add Great Expectations for data quality checks.

Connect to Power BI/Tableau for visualization.

Automate deployments with GitHub Actions + Astro CLI.

### Author

Yusuf Adetona

📧 yustone003@yahoo.com

🔗 LinkedIn

📂 Portfolio
