# Overview

Welcome to Astronomer! This project is created after you run 'astro dev init' using the Astronomer CLI. This readme file describes the project's contents, as well as how to run Apache Airflow on your local machine.

# Weather Data ETL Project

# Introduction

This project demonstrates an automated ETL (Extract, Transform, Load) pipeline to collect weather data, process it, and store it in a database. The entire pipeline is managed and scheduled automatically using Apache Airflow and Astro.

# Key Features

Automation: Schedule daily runs to collect weather data.
Extract: Get weather data from the Open-Meteo API for a specific location (e.g. VIETNAM).
Transform: Convert raw JSON data into a structured format.
Load: Load processed data into a PostgreSQL database.
Monitoring: Easily monitor the status and run history of the process through the Apache Airflow user interface (UI).
Technologies used
===============
Apache Airflow: Workflow scheduling and monitoring platform.
Astro: Platform for efficient management and deployment of Airflow environments.
Python: Main programming language for ETL tasks.
Docker: Used to containerize the Airflow environment and PostgreSQL database.
PostgreSQL: Database management system for storing weather data.
Open-Meteo API: Free source of weather data.

Your Astro project contains the following files and folders:
Project Structure
===============
.
├── dags/
│ └── weather_etl.py # DAG definition file
├── docker-compose.yml # Docker service definition
├── requirements.txt # Required Python libraries
├── Dockerfile # Docker file to customize the environment
└── README.md

- dags: This directory contains the Python files for your Airflow DAGs. By default, this directory includes a sample DAG:

- `example_astronauts`: This DAG shows an example of a simple ETL pipeline, querying a list of astronauts currently in space from the Open Notify API and printing a statement for each astronaut. The DAG uses the TaskFlow API to define tasks in Python and dynamically maps the tasks to print a dynamic command for each astronaut. To learn more about how this DAG works, see our [Getting Started with Airflow Guide].

- Dockerfile: This file contains the versioned Astro Runtime Docker image, which provides a distinct Airflow experience. If you want to execute other commands or overrides at runtime, specify them here.

- include: This directory contains any additional files you want to include in the project. By default, this directory is empty.

- packages.txt: Install the operating system-level packages required for your project by adding them to this file. By default, this directory is empty.

- requirements.txt: Install the Python packages required for your project by adding them to this file. By default, this directory is empty.

- requirements.txt: Install the Python packages required for your project by adding them to this file. By default, this directory is empty.

- plugins: Add custom or community plugins for your project to this file. By default, this directory is empty.

- airflow_settings.yaml: Use this local-only file to specify Airflow Connections, Variables, and Groups instead of importing them into the Airflow UI when you develop DAGs in this project.

# Deploy Local Project_Install and Use

1. Install Astro CLI: Follow the instructions on the Astro homepage to install the command line tool.
2. Initialize the project:
   mkdir etl_weather_project
   cd etl_weather_project
   astro dev init
3. Start the environment:
   astro dev start

This command will launch five Docker containers on your machine, each for a different Airflow component:

- Postgres: Airflow's Metadata database
- Scheduler: Airflow component responsible for monitoring and triggering tasks
- DAG Processor: Airflow component responsible for parsing the DAG
- API Server: Airflow component responsible for serving the Airflow UI and API
- Triggerer: Airflow component responsible for triggering delayed tasks

4. Access the UI: Once started, access the Airflow UI at http://localhost:8080 to view the DAG and trigger tasks.

Once all five containers are ready, the command will open a browser to the Airflow UI at http://localhost:8080/. You can also access your Postgres Database at 'localhost:5432/postgres' with the username 'postgres' and password 'postgres'.

5. Edit the DAG: Customize the parameters in your DAG file (e.g. dags/weather_etl.py) to change the location or schedule.

6. Test the data: Connect to the PostgreSQL database to test the loaded data.

Note: If you have been allocated one of the above two ports, you can [stop existing Docker containers or change the port](https://www.astronomer.io/docs/astro/cli/troubleshoot-locally#ports-are-not-available-for-my-local-airflow-webserver).

# Deploying your project to Astronomer

If you have an Astronomer account, pushing code to an Astronomer deployment is simple. For deployment instructions, see the Astronomer documentation: https://www.astronomer.io/docs/astro/deploy-code/
