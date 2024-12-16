# WeatherStream ETL

![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=apache-airflow&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Astronomer](https://img.shields.io/badge/Astronomer-342C59?style=for-the-badge&logo=astronomer&logoColor=white)
 
Welcome to my **ETL Weather Project**! This project automates the **extraction**, **transformation**, and **loading (ETL)** of weather data from a public API into a **Postgres database** using **Apache Airflow** for workflow orchestration. It showcases a scalable and modular ETL pipeline, ideal for real-world data processing and analytics.

---

## **Project Overview**  

The **ETL Weather Project** is designed to demonstrate a robust and reliable ETL pipeline, leveraging industry-standard tools to process weather data.  

### **Key Features**:
- **Automated ETL Pipeline**: Automatically fetch, clean, and load weather data into a database.
- **Workflow Orchestration**: Manage and monitor all tasks using Apache Airflow.
- **Data Integrity**: Handle missing values, clean raw data, and ensure consistency for analysis.
- **Scalability**: Build a reusable framework for expanding to other data sources.

---

## **ETL Workflow**  

1. **Extract**: Retrieve weather data from a public API (e.g., [OpenWeatherMap](https://openweathermap.org/api)) in **JSON** format. Data includes:  
   - Temperature  
   - Humidity  
   - Weather conditions  
   - Timestamps  

2. **Transform**:  
   - Standardize timestamps for time zone consistency.  
   - Handle missing or erroneous values.  
   - Convert and clean raw data for analysis-ready storage.  

3. **Load**: Insert processed data into a **Postgres database** for long-term storage and analysis.

---

## **Project Structure**  

The project is organized into the following directories and files:  

- **`dags/`**:  
  - Contains Airflow **DAGs (Directed Acyclic Graphs)** that define the ETL pipeline.  
  - `etlweather.py`: Main DAG implementing the ETL process.  

- **`requirements.txt`**: Specifies Python dependencies, such as:  
  - `requests`: For API calls.  
  - `pandas`: For data transformation.  
  - `psycopg2`: For Postgres integration.  

- **`airflow_settings.yaml`**: Configures connections, including:  
  - API Key and Endpoint.  
  - Database credentials.  

- **`Dockerfile`**: Defines the Airflow runtime environment using Docker.  
- **`plugins/`**: Placeholder for custom Airflow plugins (currently empty).  
- **`packages.txt`**: Placeholder for OS-level package installations.  

---

## **Setup Instructions**  

### **Run the Project Locally**  

1. **Start Airflow**:  
   Use Astronomer's CLI to start the project locally:  
   ```bash
   astro dev start
   ```  

   This will spin up Docker containers for:  
   - **Postgres**: Used as the Airflow metadata database and storage for ETL data.  
   - **Webserver**: Provides the Airflow UI at [http://localhost:8080/](http://localhost:8080/).  
   - **Scheduler**: Triggers and monitors task execution.  

2. **Access the Airflow UI**:  
   - Navigate to: [http://localhost:8080/](http://localhost:8080/)  
   - Login credentials: `admin` / `admin`.  

3. **Connect to the Postgres Database**:  
   - Default host: `localhost:5432`.  
   - Inspect or query weather data directly in the database.

---

## **API and Database Configuration**  

1. **Weather API Key**:  
   - Obtain an API key (e.g., from [OpenWeatherMap](https://openweathermap.org/api)).  
   - Add the key in `airflow_settings.yaml` or set it as an environment variable.

2. **Database Configuration**:  
   - Define database credentials in `airflow_settings.yaml` for seamless integration.

---

## **Troubleshooting**  

### Common Issues and Fixes:  

1. **Port Conflicts**:  
   - If ports `8080` (Airflow UI) or `5432` (Postgres) are already in use, modify the Docker port settings in the `astro` configuration.  

2. **API Key Errors**:  
   - Double-check that the API key is valid and properly configured in the settings.  

3. **Database Connectivity Issues**:  
   - Ensure the database credentials are accurate and the Postgres service is running.  

---

## **Screenshots**  

Here are some screenshots showcasing the project setup and Airflow UI:  

![Airflow UI Screenshot](https://github.com/user-attachments/assets/a339fb94-dfb6-4068-b58a-d4ac52baf152)  
![Database View Screenshot](https://github.com/user-attachments/assets/2f7cf81a-e591-4a93-92df-b25686c7fe79)  



