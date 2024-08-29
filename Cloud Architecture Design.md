# Cloud Architecture Design Summary

## Overview
For this project, which involves transforming a JSON dataset into a CSV format, I propose using Google Cloud services (GCS). The architecture is designed with security, scalability, and cost-efficiency in mind.

## Google Cloud Tech Stack
1. **Google Cloud Storage (GCS)**: The raw JSON dataset is first uploaded to a designated GCS bucket, which triggers the data processing pipeline.
2. **Google Cloud Functions**: Cloud Functions process the uploaded JSON data using Python, transforming it into a CSV file and saving it back to the GCS bucket.
3. **Google BigQuery**: The generated CSV file can be loaded into BigQuery, where it can be queried and analysed at scale to derive insights.

## Complementary Tech Stack
1. **Apache Airflow**: Airflow can be used to schedule and automate the ETL (Extract, Transform, Load) pipeline, ensuring that the workflow runs at predefined intervals or based on specific triggers.
2. **dbt (Data Build Tool)**: dbt enables modularity and reusability in data modeling. It also integrates version control and promotes collaboration, ensuring data transformations are well-documented and managed.
3. **Airflow + dbt Integration**: Integrating dbt with Airflow allows for orchestration of dbt models within complex data pipelines. This combination enables automated workflows and ensures that all components of the ETL pipeline execute in the correct order.

## Key Considerations
1. **Security**: Google Cloud Identity and Access Management (IAM) roles are implemented to control access to the GCS bucket and other resources. This ensures that only authorised users and services can access and modify the data, safeguarding sensitive information.
2. **Scalability**: By utilising serverless services like Cloud Functions, the solution automatically scales based on the size of the data being processed. These services dynamically allocate resources, ensuring optimal performance even as the workload fluctuates.
3. **Cost-Efficiency**: The pay-as-you-go pricing model of Google Cloud services helps minimise costs, as you only pay for the resources you use. For example, in Google BigQuery, you are billed based on the amount of data processed by your queries, making it a cost-effective solution for large-scale analytics.

# Cloud Architecture Diagram
For a visual representation of the cloud architecture, please refer to the diagram below:

[![Cloud Architecture Diagram](https://drive.google.com/uc?export=view&id=1rqhz2Lu9GE44YBH7fhyOi8UvzzYlKEQj)](https://drive.google.com/file/d/1rqhz2Lu9GE44YBH7fhyOi8UvzzYlKEQj/view?usp=sharing)


