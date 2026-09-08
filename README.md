# Ride Analytics & Revenue Intelligence Dashboard

**Zyroo Internship Program — Data Analytics Track, Week 2, Task 01**

## Objective
Clean a small ride-hailing dataset, calculate basic KPIs, and build a simple analytics dashboard.

## Dataset
- **Source:** Synthetic sample ride-hailing dataset created for this task (`data/raw_rides.csv`).
- **Columns:** Ride ID, Date, Pickup Location, Drop-off Location, Fare, Payment Method, Ride Status, Rating.
- **Raw rows:** 126 (intentionally includes duplicates, blanks, a negative fare, and a bad date to simulate real-world messiness).

## Data Cleaning Steps
1. Removed duplicate Ride IDs (kept first occurrence) — **1 row removed**.
2. Removed rows with empty Pickup Location or Date — **2 rows removed**.
3. Removed rows with an unparseable date format — **1 row removed**.
4. Converted Fare to numeric and removed rows where Fare was missing/non-numeric — **1 row removed**.
5. Removed rows with a negative Fare — **1 row removed**.
6. Standardized Date to `YYYY-MM-DD` format.
7. **Final cleaned dataset: 120 rows** (`data/cleaned_rides.csv`).

## KPIs Calculated
| KPI | Value |
|---|---|
| Total Rides | 120 |
| Completed Rides | 96 |
| Cancelled Rides | 24 |
| Total Revenue | PKR 65,427 |
| Average Fare | PKR 682 |
| Average Rating | 3.96 / 5 |

## Dashboard
`powerbi/Ride_Analytics_Dashboard.xlsx` contains:
- A **KPI Dashboard** sheet with all KPIs computed live with formulas (SUMIFS/COUNTIF/AVERAGEIFS) from the cleaned data.
- A **Charts** sheet with:
  - Rides by Date
  - Revenue by Date
  - Rides by Payment Method
  - Rides by Status
  - Top Pickup Locations
- An **Insights** sheet with written takeaways.

This workbook can be used directly as the Power BI data source: open Power BI Desktop → **Get Data → Excel Workbook** → select `Ride_Analytics_Dashboard.xlsx` → load the **Cleaned Data** sheet → recreate the KPI cards and charts above using Power BI's Card and Chart visuals.

## Business Insights
1. Out of 120 cleaned rides, 96 were completed and 24 were cancelled — a 20% cancellation rate worth investigating.
2. Card is the most-used payment method (45 rides), narrowly ahead of Cash (42) and Wallet (33).
3. Johar Town is the busiest pickup location with 21 rides, followed by Model Town (19) and Wapda Town (18).
4. Total revenue from completed rides is PKR 65,427, with an average fare of about PKR 682 per completed ride.
5. Average customer rating across completed rides is 3.96 out of 5, suggesting room to improve service quality.

## Tools Used
- Python (pandas) for data cleaning
- Excel (openpyxl) for the KPI dashboard and charts
- Power BI (recommended) for the final interactive dashboard

## Project Structure
```
ride-analytics/
├── data/
│   ├── raw_rides.csv
│   └── cleaned_rides.csv
├── powerbi/
│   └── Ride_Analytics_Dashboard.xlsx
├── screenshots/
└── README.md
```
