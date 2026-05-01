# ClearVue Ltd – NoSQL BI System

##  Overview
ClearVue Ltd’s BI system is designed to solve the challenge of generating timely and accurate sales reports aligned with its custom financial calendar.  
This project integrates **MongoDB Atlas**, **Apache Kafka**, **Python ETL scripts**, and **Power BI** to deliver flexible querying, real-time reporting, and supplier analytics.

---

##  Features
- Centralized NoSQL database using **MongoDB Atlas**.
- Real-time payment transaction streaming with **Apache Kafka**.
- **Python ETL scripts** for data cleaning, transformation, and pipeline management.
- Interactive **Power BI dashboards** with DirectQuery for live analytics.
- Secure **Flask API layer** with endpoints for querying and reporting.

---

## System Architecture
- **MongoDB Atlas** – Stores collections (`sales_header`, `sales_line`, `payment_lines`, `suppliers`, `payments_stream`).  
- **Apache Kafka** – Produces and consumes JSON-formatted transaction messages.  
- **Python ETL** – Bridges Kafka and MongoDB, ensuring clean structured records.  
- **Power BI** – Connects directly to MongoDB for dashboards and analytics.  
- **Flask API Layer** – Provides secure endpoints (`sales_summary`, `top_products`, `real_time_updates`, etc.).

---

##  Data Flow
1. **Data Sources** – CSV imports + Kafka streams.  
2. **Kafka Producer** – Publishes payment events.  
3. **Kafka Consumer** – Inserts into MongoDB `payments_stream`.  
4. **MongoDB Atlas** – Hosts cleaned and aggregated data.  
5. **Power BI** – Visualizes sales, payments, suppliers, and customer performance.

---

##  Collections & Models
| Collection       | Purpose |
|------------------|---------|
| `sales_header`   | Transaction metadata (customer, date, type). |
| `sales_line`     | Product-level details (quantity, price, cost). |
| `payment_lines`  | Customer payments (amounts, discounts, references). |
| `suppliers`      | Supplier information (terms, credit limits). |
| `payments_stream`| Real-time payment feed via Kafka. |

---

##  Dashboards
- **Sales Trends Dashboard** – Daily/weekly/monthly/quarterly sales aligned to ClearVue’s custom financial calendar.  
- **Customer Performance Dashboard** – Spending, balances, overdue payments.  
- **Supplier Analytics Dashboard** – Purchases, margins, supplier performance.  
- **Real-Time Transactions Monitor** – Live Kafka-fed payments, auto-refresh every 2–3 seconds.  

---

##  Setup Instructions
### Prerequisites
- Python 3.9+
- MongoDB Atlas account
- Apache Kafka
- Power BI Desktop

### Installation

git clone https://github.com/your-repo/ClearVue_Project.git
cd ClearVue_Project
pip install -r requirements.txt

###Configuration
Update config.json with:
MongoDB URI
Kafka broker details
API keys

## Run ETL
-python etl_pipeline.py
Start API
-python app.py

### Security
Authentication: OAuth2 / secure tokens.

Authorization: Role-based access control (RBAC).

IP Restrictions: Controlled access by role.

Secure Transmission: HTTPS enforced for all communications.

### Testing & Validation
Unit tests for aggregation pipelines.

Data type normalization (customer codes, dates).

Duplicate removal and field verification.

Error handling with logging and fallback strategies.
