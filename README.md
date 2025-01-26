# Real-Time Ticket Booking Data Sync Pipeline

## Project Overview

This project demonstrates an end-to-end real-time data engineering pipeline using Google Cloud Platform (GCP) services for processing and syncing ticket booking data.

## Architecture

The pipeline consists of the following key components:
- Pub/Sub for real-time data streaming
- Data Flow for data transformation and processing
- BigQuery for data storage and analytics

### Key Technologies
- Python
- Google Cloud Pub/Sub
- Google Cloud Data Flow
- BigQuery
- Apache Beam

## Project Setup

### Prerequisites
- Google Cloud Platform account
- Python 3.7+
- Google Cloud SDK
- Required GCP APIs enabled:
  - Pub/Sub
  - BigQuery
  - Data Flow

### Service Account Permissions
Ensure your service account has the following roles:
- BigQuery Admin
- Pub/Sub Admin
- Data Flow Admin

## Pipeline Components

### 1. Data Generation
- Python script generates mock ticket booking data
- Publishes data to Pub/Sub topic (e.g., `IRCTC-data`)

### 2. Data Transformation
- Data Flow job processes incoming Pub/Sub messages
- Custom Python UDF for data transformation
- Handles:
  - Data cleaning
  - Column derivation
  - Data enrichment

### 3. Data Destination
- Transformed data synced to BigQuery table
- Supports at-least-once and exactly-once processing
- Error handling with dead-letter queue for failed records

## Key Features
- Real-time data streaming
- Flexible data transformation
- Scalable architecture
- Error resilience
- GCP managed services

## Sample Transformation Logic
- Standardize column names
- Capitalize names
- Lowercase emails
- Add default values
- Derive loyalty status
- Add timestamp columns

## Deployment Steps
1. Create Pub/Sub topic
2. Set up BigQuery dataset and table
3. Configure Data Flow job
4. Deploy Python mock data generator
5. Start Data Flow pipeline

## Monitoring
- Check Data Flow job logs
- Monitor BigQuery table for ingested records
- Review error records table for failed transformations

## Potential Use Cases
- Ticket booking platforms
- Change Data Capture (CDC)
- Real-time event processing
- Customer data synchronization

## Future Improvements
- Add more complex transformations
- Implement data validation
- Create real-time dashboards
- Add monitoring and alerting

## References
- Apache Beam Documentation
- Google Cloud Data Flow Templates
- BigQuery streaming insert documentation
