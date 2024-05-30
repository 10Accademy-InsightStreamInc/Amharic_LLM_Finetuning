# Scalable Data Warehouse for LLM Finetuning: API Design for High Throughput Data Ingestion and RAG Retrieval

## Project Overview

This projects aims to enhance Natural Language Processing (NLP) capabilities for African languages, focusing on Amharic. This project aims to develop a comprehensive data corpus to support various NLP applications, such as semantic search, content generation, chatbot support, sentiment analysis, and speech recognition.

## Table of Contents

- [Project Overview](#project-overview)
- [Business Need](#business-need)
- [Contributors](#team-members)
- [Tech Stack](#tech-stack)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Business Need

The lack of extensive, high-quality text/audio datasets for Amharic is a significant bottleneck for developing competitive NLP products. By collecting and processing a vast amount of text/audio data from diverse online sources, this project will enhance Roots Tech Solutions' ability to create innovative NLP tools for these languages.

## Contributors

- Abubeker Shamil
- Michael George
- Nyamusi Moraa
- Eyerusalem Admassu

## Tech Stack

- **Programming Languages:** Python, JavaScript (React)
- **Web Scraping Tools:** Selenium
- **Database:** PostgreSQL
- **API Frameworks:** Flask
- **Containerization:** Docker, Docker Compose
- **Workflow Automation:** Apache Airflow
- **Annotation Tool:** Prodigy
- **Monitoring:** Grafana

## Setup Instructions

### Prerequisites

- Python 3.x
- Docker and Docker Compose
- PostgreSQL or MongoDB (for local development)

### Installation

1. **Clone the Repository**
   ```sh
   git clone https://github.com/your-username/your-repository.git
   cd your-repository
   ```
2. **Set Up Virtual Environment**
   ```sh
   Copy code
   python3 -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```
3. **Install Requirements**
   ```sh
   pip install -r requirements.txt
   Set Up Environment Variables
   ```
4. **Set Up Virtual Environment**
   Create a .env file and add the following variables
   ```env
   DB_USERNAME='your_username'
   DB_PASSWORD='your_password'
   DB_HOST='your_host'
   DB_PORT=port
   DB_DATABASE='db_name'
   ```
5. **Run Docker Compose**

   ```sh
   docker-compose up --build
   ```

6. **Run Web Scraping Scripts**

   ```sh
   python scrapper/news_sites/alain.py
   ```

7. **Normalize and Clean Text Data**

   ```sh
   python scripts/clean_data.py
   ```

8. **Filter Data for Amharic**

   ```sh
   python scripts/filter_data.py
   ```

## API Development

**Run FastAPI Application**

```sh
cd api
fastapi dev main.py
```

## Automation & Stream Processing

**Set Up Apache Airflow**

```sh
airflow db init
airflow webserver --port 8080
airflow scheduler
```

## Code Structure

    ├── app
    │   ├── main.py               # API entry point
    │   ├── routes                # API routes
    │   ├── view_models           # Pydantic models (schemas)
    │   ├── controllers           # Business logic
    │   └── models                # SQLAlchemy models
    ├── data/raw
    │   ├── alain_news.csv        # Raw data files
    │   └── ...
    ├── schema
    │   ├── news_schema.sql       # SQL schema for news
    │   └── ...
    ├── db/connection
    │   ├── db_connection.py      # db connection script
    │   └── ...
    ├── scrapper
    │   ├── news_sites/           # News sites scrapping scripts
    │   ├── telegram/             # Telegram Scrapping scripts
    │   ├── other/                # Other sites scripts
    │   └── ...
    ├── Dockerfile                # Docker configuration
    ├── docker-compose.yml        # Docker Compose configuration
    ├── requirements.txt          # Python dependencies
    ├── README.md                 # Project documentation
    └── ...

### Contributing

Contributions are welcome! Please follow these steps:

- Fork the repository.
- Create a new branch.
- Make your changes.
- Submit a pull request.

### License

This project is licensed under the MIT License. See the LICENSE file for details.

### Next Steps

1. **Populate the Repository:** Ensure the repository has the necessary scripts (`scrapy_spider.py`, `clean_data.py`, `filter_data.py`) and configuration files (`Dockerfile`, `docker-compose.yml`).
2. **Document Individual Scripts:** Add comments and documentation within each script to explain its functionality.
3. **Setup AWS Resources:** Configure AWS resources (EC2, S3, RDS, Kinesis) as needed for your specific project requirements.
4. **Collaborate and Communicate:** Share the repository link with your team members and collaborate using issues and pull requests for any changes or improvements.
