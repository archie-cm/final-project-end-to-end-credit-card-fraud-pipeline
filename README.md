# Credit Card Fraud Pipeline Subscription End-to-End Data Pipeline

## Bussiness Understanding

Credit score is an important metric for banks to rate the credit performance of their applicants. 
They use personal information and financial records of credit card applicants to predict whether these applicants will default in the future or not. 
From these predictions, the banks will then decide if they want to issue credit cards to these applicants or not. 
The banks are asking us to create an end-to-end pipeline to help them handle this problem. 
The original datasets and data dictionary can be found in [here](https://www.kaggle.com/datasets/rikdifos/credit-card-approval-prediction).

## Problem Statements

From said back story, we can conclude that the bank want to increase the efficiency of their campaign by targeting client with higher chance of success based on the feature from the data.

## Project Objectives
The objectives of this projects are described below:
- Create an automated pipeline to flow both batch and stream data from data sources to data warehouses and data marts.
- Create a visualization dashboard to get insights from the data, which can be used for business decisions.
- Create an infrastructure as code which makes the codes reusable and scalable for another projects.

## End-to-End Schema with Lambda Architecture
##### enter the directory

##### Create infrastructure with Docker Compose
```bash
sudo docker-compose up
```

##### Install required Python packages
```bash
pip install -r requirements.txt
```

##### Run the producer to stream the data into the Kafka topic
```bash
python3 producer.py
```

##### Run the consumer to consume the data from Kafka topic and load them into BigQuery
```bash
python3 consumer.py
```

##### Open Spark to monitor Spark master and Spark workers
```
localhost:8080
```

##### Open Airflow with username and password "airflow" to run the DAG
```
localhost:8090
```

##### Open Kafka Connect to view the active connectors
```
localhost:8083/connectors
```

##### Open Schema Registry to view the active schemas
```
localhost:8081/schemas
```

## Tools
Orchestration: Airflow

Storage: Google Cloud Storage

Warehouse: BigQuery

Data Visualization: Tableau

## Reproducibility

## Data Visualization Dashboard

## Google Cloud Usage Billing Report
Data infrastructure we used in this project are entirely built on Google Cloud Platform with more or less 3 weeks of project duration, 
using this following services:
- Google Cloud Storage (pay for what you use)
- Google BigQuery (first terrabyte processed are free of charge)
- Google Looker Studio (cost is based from number of Looker Blocks (data models and visualizations), users, and the number of queries processed per month)
- Pub/sub (cost is based from amount of data exchanged)
- Dataflow (cost is based on duration of processing job and number of resources utilized)
> Total cost around 51$ out of 300$ free credits that GCP provided

## Resources

