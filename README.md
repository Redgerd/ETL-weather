# ETL Weather Project

Welcome to the ETL Weather Project! This project automates the extraction, transformation, and loading (ETL) of weather data from a public API into a database using Apache Airflow for workflow orchestration.

## Project Overview

This project demonstrates an ETL pipeline that:

- **Extracts** weather data from a public weather API.
- **Transforms** the data by cleaning, standardizing timestamps, and handling missing values.
- **Loads** the processed data into a Postgres database for analysis.

## Project Structure

The project directory includes the following files and folders:

- **`dags`**: Contains the Airflow DAGs, including:
  - `etlweather.py`: Implements the ETL pipeline for weather data.
- **`requirements.txt`**: Lists Python dependencies, such as `requests`, `pandas`, and `psycopg2`.
- **`airflow_settings.yaml`**: Used to define Airflow connections (e.g., API and database credentials).
- **`Dockerfile`**: Defines the Airflow runtime environment for this project.
- **`plugins`**: Placeholder for custom Airflow plugins (empty by default).
- **`packages.txt`**: Placeholder for OS-level packages (empty by default).

## Setup Instructions

### Running Locally

1. **Start Airflow**:
   Run the following command to start the project:

   ```bash
   astro dev start
   ```

   This spins up Docker containers for:

   - **Postgres**: Metadata database.
   - **Webserver**: Airflow UI.
   - **Scheduler**: Monitors and triggers tasks.

2. **Access the Airflow UI**:

   - URL: [http://localhost:8080/](http://localhost:8080/)
   - Credentials: `admin` / `admin`.

3. **Connect to Postgres**:
   Access the database at `localhost:5432` for inspecting the loaded weather data.

### API and Database Configuration

1. **Weather API Key**:

   - Obtain an API key (e.g., from [OpenWeatherMap](https://openweathermap.org/api)).
   - Set it in `airflow_settings.yaml` or as an environment variable.

2. **Database Configuration**:
   - Configure database credentials in `airflow_settings.yaml` for seamless connection.

## ETL Pipeline Workflow

1. **Extract**: Fetches weather data (e.g., temperature, humidity, and conditions) from the API in JSON format.
2. **Transform**: Cleans and standardizes data for consistent storage.
3. **Load**: Inserts the processed data into a Postgres database.

## Troubleshooting

- **Port Conflicts**: Adjust Docker port settings if 8080 or 5432 are in use.
- **API Key Errors**: Verify the API key's validity and configuration.
- **Database Issues**: Ensure proper connection settings in `airflow_settings.yaml`.
