# RetailSync ETL Pipeline

<div align="center">
  <p><strong>A robust ETL pipeline for processing and analyzing retail transaction data</strong></p>
  <p>
    <a href="#overview">Overview</a> •
    <a href="#project-architecture">Architecture</a> •
    <a href="#key-features">Features</a> •
    <a href="#data-processing">Data Processing</a> •
    <a href="#installation">Installation</a> •
    <a href="#usage">Usage</a> •
    <a href="#requirements">Requirements</a>
  </p>
</div>

## Overview

RetailSync ETL Pipeline is a sophisticated data engineering solution that implements a complete Extract, Transform, Load (ETL) pipeline for processing retail transaction data. The pipeline extracts data from Amazon Redshift, performs various data quality transformations, and loads the processed data into Amazon S3 for further analysis and business intelligence applications.

## Project Architecture

### Pipeline Components
1. **Extract (Amazon Redshift)**
   - Connects to Redshift warehouse
   - Extracts online transactions data
   - Performs initial SQL transformations
   - Handles data type conversions

2. **Transform (Python)**
   - Data validation and cleaning
   - Duplicate record management
   - Data quality enhancement
   - Business logic implementation

3. **Load (Amazon S3)**
   - AWS S3 integration
   - CSV file generation
   - Secure data upload
   - Success verification

### Data Flow
```
[Amazon Redshift] → Extract → Transform → Load → [Amazon S3]
```

## Key Features

- **🔄 Automated ETL Workflow**
  - Streamlined data extraction
  - Intelligent transformation rules
  - Efficient loading process

- **🧹 Data Quality Management**
  - Duplicate detection and removal
  - Null value handling
  - Data type validation
  - Business rule enforcement

- **☁️ Cloud Integration**
  - Amazon Redshift connectivity
  - S3 storage integration
  - Secure credential management

- **🔒 Security & Compliance**
  - Environment variable protection
  - Credential encryption
  - Access control implementation

## Data Processing

### Extract Phase
- Connects to Amazon Redshift data warehouse
- Extracts data from online_transactions and stock_description tables
- Applies SQL-level transformations:
  - Filters invalid customer IDs
  - Removes specific stock codes
  - Handles null descriptions
  - Formats dates
  - Calculates order values

### Transform Phase
- Identifies and removes duplicate records
- Maintains data integrity
- Provides transformation metrics
- Ensures data quality standards

### Load Phase
- Establishes secure S3 connection
- Converts data to CSV format
- Uploads to specified S3 bucket
- Verifies successful transfer

## Installation

### Prerequisites
- Python 3+
- Docker (optional)
- AWS Account with S3 access
- Redshift database access

### Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone https://github.com/VaibhavDaveDev/RetailSync-ETL-Pipeline.git
   cd RetailSync-ETL-Pipeline
   ```

2. **Environment Configuration**
   ```bash
   cp .env.example .env
   # Configure your environment variables in .env file
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Command Line Execution

1. **Direct Python Execution**
   ```bash
   # Windows
   python main.py

   # Mac/Linux
   python3 main.py
   ```

2. **Docker Execution**
   ```bash
   # Build Docker image
   docker image build -t retail-sync-etl .

   # Run ETL job
   docker run --env-file .env retail-sync-etl
   ```

## Requirements

### System Requirements
- Python 3+
- Docker (optional)
- 4GB RAM minimum

### Python Dependencies
- pandas
- psycopg2-binary
- boto3
- python-dotenv

### Environment Variables
```
# Redshift Configuration
dbname=            # Database name
host=              # Host address
port=              # Port number
user=              # Username
password=          # Password

# AWS Configuration
aws_access_key_id= # AWS access key
aws_secret_access_key_id= # AWS secret key
```

## Project Structure
```
RetailSync-ETL-Pipeline/
├── src/
│   ├── extract.py          # Redshift data extraction
│   ├── transform.py        # Data transformation logic
│   └── load_data_to_s3.py  # S3 upload functionality
├── main.py                 # Pipeline orchestration
├── requirements.txt        # Dependencies
├── Dockerfile             # Container configuration
├── .env.example          # Environment template
├── .dockerignore         # Docker exclusions
└── .gitignore           # Git exclusions
```

<div align="center">
  <p>
    <a href="https://github.com/VaibhavDaveDev/RetailSync-ETL-Pipeline/stargazers">⭐ Star this repo</a> •
    <a href="https://github.com/VaibhavDaveDev/RetailSync-ETL-Pipeline/issues/new">🐛 Report bug</a> •
    <a href="https://github.com/VaibhavDaveDev/RetailSync-ETL-Pipeline/issues/new">✨ Request feature</a>
  </p>
</div>