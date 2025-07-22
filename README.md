# Data Ingestion from S3 to RDS with Fallback to AWS Glue using Dockerized Python Application

## 📌 Overview
This project implements an **automated** and **fault-tolerant** data ingestion pipeline using **AWS S3**, **RDS**, **Glue**, and **Docker**. The system reads CSV data from S3, attempts to insert it into an **RDS (MySQL-compatible)** database, and if that fails, it falls back to **AWS Glue** for cataloging the data.

---

## 🎯 Objectives
- ✅ Automate CSV data ingestion from **S3 to RDS**
- 🔄 Implement a fallback mechanism to **AWS Glue** in case of RDS failure
- 📦 Containerize the solution using **Docker** for portability and scalability

---

## ⚙️ Tech Stack

| Component        | Technology                  |
|------------------|------------------------------|
| Programming      | Python 3.9+                  |
| Cloud Services   | AWS S3, RDS (MySQL), AWS Glue|
| Containerization | Docker                       |
| Libraries        | `boto3`, `pandas`, `sqlalchemy`, `pymysql` |

---

## 🏗 Architecture

    +---------------+
    |   CSV File    |
    |  (Stored S3)  |
    +-------+-------+
            |
            v
    +-------+-------+
    | Dockerized    |
    | Python Script |
    +-------+-------+
            |
    +-------v-------+
    |  Attempt RDS  |
    |  Insertion    |
    +-------+-------+
            |
    Success | Failure
            v
    +---------------+       +--------------------+
    |  RDS Database |       | AWS Glue Data      |
    |               | <---> | Catalog Table (S3) |
    +---------------+       +--------------------+

    
---

## 📥 Clone and Run

```bash
git clone https://github.com/abhighante37/S3toRDS-FallbackGlue

