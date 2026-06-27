# OLA Ride Analytics Dashboard
**Tools:** Python (Pandas) | SQL (MySQL) | Streamlit | Power BI  
**Domain:** Operations Analytics | Ride-Hailing | Business Intelligence  
**Dataset:** OLA ride bookings dataset — vehicle types, booking status, cancellations, ratings, payment methods

---

## 🚀 Live Dashboard
👉 [**Click here to view the live Streamlit app**](https://app-dashboard-kj7p97d8kzfmfu5agcpz5t.streamlit.app/)

---

## Project Overview

An end-to-end operations analytics project on OLA ride booking data — combining SQL-based data extraction, Python-powered data processing, and interactive dashboard deployment via Streamlit. The project answers key business questions around ride performance, cancellation patterns, vehicle utilisation, and payment behaviour.

---

## Business Questions Answered

| # | Business Question | Method |
|---|---|---|
| 1 | Which vehicle type covers the most ride distance? | SQL + Aggregation |
| 2 | Total rides per vehicle type | SQL + GROUP BY |
| 3 | What are the top reasons customers cancel rides? | SQL + ORDER BY |
| 4 | Who are the top 5 most frequent customers? | SQL + LIMIT |
| 5 | Average ride distance by vehicle type | SQL + AVG |
| 6 | Cancellations due to personal/car-related issues | SQL + WHERE filter |
| 7 | Max and min driver ratings for Prime Sedan | SQL + IN clause |
| 8 | Total booking value via UPI payments | SQL + SUM + filter |
| 9 | Average customer rating per vehicle type | SQL + AVG + GROUP BY |
| 10 | Total revenue from successful rides | SQL + SUM + filter |
| 11 | Incomplete rides breakdown by reason | SQL + GROUP BY + ORDER BY |

---

## Key Features

- **File Upload Support** — users can upload their own dataset (xlsx) for instant analysis
- **Pivot Table Analysis** — vehicle type vs booking status cross-tabulation
- **Interactive Streamlit UI** — accessible to non-technical users without SQL or Python knowledge
- **Power BI Dashboard** — complementary visual report built in Power BI with multi-page layout

---

## SQL Highlights

```sql
-- Top 5 customers by ride count
SELECT Customer_ID, COUNT(*) AS total_rides
FROM oladataset
GROUP BY Customer_ID
ORDER BY total_rides DESC
LIMIT 5;

-- Average ride distance by vehicle type (successful rides only)
SELECT Vehicle_Type, SUM(Ride_Distance) AS total_ride_distance
FROM oladataset
WHERE Booking_Status = 'Success'
GROUP BY Vehicle_Type;

-- Incomplete rides breakdown
SELECT Incomplete_Rides_Reason, COUNT(*) AS rides_count
FROM oladataset
WHERE Incomplete_Rides_Reason <> 'null'
GROUP BY Incomplete_Rides_Reason
ORDER BY rides_count DESC;
```

---

## Tech Stack

| Layer | Tool |
|---|---|
| Data Extraction | SQL (MySQL) |
| Data Processing | Python — Pandas |
| Dashboard App | Streamlit |
| BI Reporting | Power BI (Power Query) |
| Data Source | Excel (.xlsx) |

---

## Files in This Repo

| File | Description |
|---|---|
| `streamlit.st.py` | Main Streamlit dashboard application |
| `OLA_DataSet.xlsx` | Source dataset |
| `requirements.txt` | Python dependencies |
| `SQL QUERIES.docx` | All 11 SQL queries with business context |
| `PROJECT 3 - POWER QUERY QUESTIONS.pbix` | Power BI report file |

---

## How to Run Locally

```bash
# Clone the repo
git clone https://github.com/Jawahar007j/Streamlit-Dashboard.git
cd Streamlit-Dashboard

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run streamlit.st.py
```

---

## Connect

[LinkedIn](https://linkedin.com/in/jawahar-ranganathan) | [GitHub](https://github.com/Jawahar007j)
