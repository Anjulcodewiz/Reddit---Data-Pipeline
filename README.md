# Reddit -Data-Pipeline

Data Pipeline with Reddit, Airflow, Celery, Postgres, S3, AWS Glue, Athena, and Redshift

This project provides a comprehensive data pipeline solution to extract, transform, and load (ETL) Reddit data into a Redshift data warehouse. The pipeline leverages a combination of tools and services including Apache Airflow, Celery, PostgreSQL, Amazon S3, AWS Glue, Amazon Athena, and Amazon Redshift.

## Overview

The pipeline is designed to:

- Extract data from Reddit using its API.
- Store the raw data into an S3 bucket from Airflow.
- Transform the data using AWS Glue and Amazon Athena.
- Load the transformed data into Amazon Redshift for analytics and querying.

## Architecture
![image](https://github.com/user-attachments/assets/eea6d703-e479-49bb-8c64-141a4d873f76)


```mermaid
graph TD
    RedditAPI((RedditAPI)) -->|Extract| Airflow[(Airflow)]
    Airflow -->|Store| S3[(S3)]
    Airflow -->|Transform| Glue[(Glue)]
    Glue -->|Transform| Athena[(Athena)]
    Athena -->|Load| Redshift[(Redshift)]
    Airflow -->|Metadata| Postgres[(Postgres)]
