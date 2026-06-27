OLA Ride Analytics Dashboard

Tools: Python (Pandas) | SQL (MySQL) | Streamlit | Power BI

Domain: Operations Analytics | Ride-Hailing | Business Intelligence

Dataset: OLA ride bookings dataset — vehicle types, booking status, cancellations, ratings, payment methods


🚀 Live Dashboard

👉 Click here to view the live Streamlit app
👉 [**Click here to view the live Streamlit app**](https://app-dashboard-kj7p97d8kzfmfu5agcpz5t.streamlit.app/)


Project Overview

An end-to-end operations analytics project on OLA ride booking data — combining SQL-based data extraction, Python-powered data processing, and interactive dashboard deployment via Streamlit. The project answers key business questions around ride performance, cancellation patterns, vehicle utilisation, and payment behaviour.


Business Questions Answered

#Business QuestionMethod1Which vehicle type covers the most ride distance?SQL + Aggregation2Total rides per vehicle typeSQL + GROUP BY3What are the top reasons customers cancel rides?SQL + ORDER BY4Who are the top 5 most frequent customers?SQL + LIMIT5Average ride distance by vehicle typeSQL + AVG6Cancellations due to personal/car-related issuesSQL + WHERE filter7Max and min driver ratings for Prime SedanSQL + IN clause8Total booking value via UPI paymentsSQL + SUM + filter9Average customer rating per vehicle typeSQL + AVG + GROUP BY10Total revenue from successful ridesSQL + SUM + filter11Incomplete rides breakdown by reasonSQL + GROUP BY + ORDER BY


Key Features


File Upload Support — users can upload their own dataset (xlsx) for instant analysis
Pivot Table Analysis — vehicle type vs booking status cross-tabulation
Interactive Streamlit UI — accessible to non-technical users without SQL or Python knowledge
Power BI Dashboard — complementary visual report built in Power BI with multi-page layout



SQL Highlights

sql-- Top 5 customers by ride count
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


Tech Stack

LayerToolData ExtractionSQL (MySQL)Data ProcessingPython — PandasDashboard AppStreamlitBI ReportingPower BI (Power Query)Data SourceExcel (.xlsx)


Files in This Repo

FileDescriptionstreamlit.st.pyMain Streamlit dashboard applicationOLA_DataSet.xlsxSource datasetrequirements.txtPython dependenciesSQL QUERIES.docxAll 11 SQL queries with business contextPROJECT 3 - POWER QUERY QUESTIONS.pbixPower BI report file


How to Run Locally

bash# Clone the repo
git clone https://github.com/Jawahar007j/Streamlit-Dashboard.git
cd Streamlit-Dashboard

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run streamlit.st.py
