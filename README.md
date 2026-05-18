# Azure Data Engineering Project – Bronze Layer Ingestion Pipeline

## Overview

This project implements an Azure Data Engineering ingestion pipeline using:

- Azure Data Factory
- Azure SQL Database
- Azure Data Lake Storage Gen2
- GitHub Integration
- Azure Integration Runtime

The pipeline extracts data from Azure SQL Database and ingests it into Azure Data Lake Storage Gen2 Bronze Layer using Azure Data Factory Copy Activity pipelines.

---

# Architecture

## Bronze Layer Ingestion Architecture

Azure SQL Database  
↓  
Azure Data Factory Pipeline  
↓  
Azure Data Lake Storage Gen2 (Bronze Layer)

---

# Tech Stack

- Azure Data Factory
- Azure SQL Database
- Azure Data Lake Storage Gen2 (ADLS Gen2)
- Azure Integration Runtime
- GitHub
- Parquet File Format

---

# Project Workflow

Pipeline workflow includes:

1. Extract data from Azure SQL Database  
2. Configure Linked Services  
3. Create Source and Sink Datasets  
4. Build Copy Activity Pipeline  
5. Load tables into Bronze Layer storage  
6. Store data in Parquet format

---

# Azure Resource Group Setup

A dedicated Azure Resource Group was created to manage all cloud resources used in the project.

## Resources Created

- Azure SQL Server
- Azure SQL Database
- Azure Data Factory
- Azure Storage Account

---

# Azure SQL Database Setup

Azure SQL Database was configured as the source system for ingestion.

## Database Configuration

- SQL Authentication enabled
- Firewall rules configured
- Azure Services access enabled

## Source Tables

Sample tables used for ingestion:

- DimUser
- DimProduct
- FactSales

---

# Azure Data Lake Storage Gen2 Setup

Azure Data Lake Storage Gen2 was created with Hierarchical Namespace enabled.

## Containers Created

- bronze
- silver
- gold

Current implementation uses only the Bronze container.

---

# Azure Data Factory Setup

Azure Data Factory was created to orchestrate ingestion pipelines and manage data movement.

---

# GitHub Integration

ADF was connected with GitHub repository for version control and collaboration.

## Git Workflow

- Main Branch
- Feature Branch
- Publish from ADF

---

# Linked Services Configuration

## Azure SQL Database Linked Service

ADF Linked Service configured for Azure SQL Database connectivity.

### Connection Details

- SQL Server Name
- Database Name
- SQL Authentication
- Azure Integration Runtime

---

## ADLS Gen2 Linked Service

ADF Linked Service configured for Azure Data Lake Storage Gen2.

### Configurations

- Storage Account
- Authentication
- Container Access

---

# Firewall Configuration

Azure SQL Server firewall rules were configured to allow Azure Data Factory access.

## Firewall Settings Enabled

- Allow Azure services and resources to access this server

---

# Dataset Configuration

## Source Dataset

Azure SQL Database tables configured as source datasets.

## Sink Dataset

ADLS Gen2 Bronze container paths configured as sink datasets.

---

# Azure Data Factory Pipeline

## Copy Activity Pipeline

A Copy Data pipeline was created to ingest Azure SQL Database tables into Bronze Layer storage.

### Pipeline Activities

- Source: Azure SQL Database
- Sink: ADLS Gen2 Bronze Layer
- File Format: Parquet
- Copy Method: Bulk Load

---

# Incremental Ingestion Pipeline

<img width="1863" height="724" alt="image" src="https://github.com/user-attachments/assets/a421ae23-bde0-41d8-b69d-bcca3c09920d" />
<img width="1863" height="724" alt="image" src="https://github.com/user-attachments/assets/664d5b87-404c-4ec8-b5a4-cf6b46c81c4a" />

# Bronze Layer Storage Structure

```text
bronze/
│
├── DimUser/
├── DimProduct/
├── FactSales/

```

