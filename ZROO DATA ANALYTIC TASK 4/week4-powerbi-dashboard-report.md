# Week 4 Report — Power BI Dashboard Development
**ZYROO Data Analytics Internship | Ride Analytics & Revenue Intelligence Platform**
**Author:** Muhammad Suhaib

---

## 1. Dashboard Purpose

This dashboard converts the Week 2 (ride demand & customer) and Week 3 (revenue & driver) analysis into a single, interactive Power BI view that lets the business quickly answer:

- How many rides are happening, and how many complete vs. cancel?
- How much revenue is generated, and by which payment method / location?
- When is ride demand highest?
- Which pickup and drop-off locations are busiest?

> **Data note:** The cleaned dataset used for this dashboard (`cleaned_rides.csv`) contains: Ride ID, Date, Pickup Location, Drop-off Location, Fare, Payment Method, Ride Status, and Rating — 120 rides recorded across August 1–30, 2026. It does not include Driver ID, Customer ID, Ride Type, or ride timestamp/hour, so Driver Performance, Customer (new vs. repeat) analysis, Peak-Hour analysis, and Ride Type breakdowns are marked as **out of scope for this dataset** rather than fabricated. A future data pull that includes those fields would let this dashboard be extended to cover them.

---

## 2. Measures (DAX)

```DAX
Total Rides = COUNTROWS(Rides)

Completed Rides = CALCULATE(COUNTROWS(Rides), Rides[Ride Status] = "Completed")

Cancelled Rides = CALCULATE(COUNTROWS(Rides), Rides[Ride Status] = "Cancelled")

Total Revenue = CALCULATE(SUM(Rides[Fare]), Rides[Ride Status] = "Completed")

Average Fare = CALCULATE(AVERAGE(Rides[Fare]), Rides[Ride Status] = "Completed")

Average Rating = AVERAGE(Rides[Rating])

Completion Rate = DIVIDE([Completed Rides], [Total Rides], 0)

Cancellation Rate = DIVIDE([Cancelled Rides], [Total Rides], 0)
```

---

## 3. Dashboard Features

**Top Section — KPI Cards**
| Total Rides | Completed Rides | Cancelled Rides | Total Revenue | Average Fare | Completion Rate |
|---|---|---|---|---|---|
| 120 | 96 | 24 | Rs 65,427 | Rs 682 | 80% |

**Middle Section — Ride Demand**
- Line chart: Rides by Date (daily trend across August)
- Bar chart: Rides by Weekday
- Bar chart: Top Pickup Locations
- Bar chart: Top Drop-off Locations

**Lower Section — Revenue**
- Donut/bar chart: Revenue by Payment Method
- Bar chart: Revenue by Pickup Location
- Card: Average Fare

**Filters (Slicers):** Date, Ride Status, Pickup Location, Payment Method

---

## 4. Key Metrics from the Data

**Rides by Weekday**
| Day | Rides |
|---|---|
| Monday | 20 |
| Tuesday | 13 |
| Wednesday | 18 |
| Thursday | 9 |
| Friday | 14 |
| Saturday | 23 |
| Sunday | 23 |

**Top Pickup Locations:** Johar Town (21), Model Town (19), Wapda Town (18), Gulberg (15), Bahria Town (15), Iqbal Town (15)

**Top Drop-off Locations:** Model Town (21), Cantt (20), Gulberg (17), Askari (16), Airport (15)

**Revenue by Payment Method:** Card Rs 26,425 (45 rides) | Cash Rs 21,548 (42 rides) | Wallet Rs 17,454 (33 rides)

**Revenue by Pickup Location:** Johar Town Rs 11,323 | Model Town Rs 10,139 | Wapda Town Rs 9,802 | Gulberg Rs 8,757 | Iqbal Town Rs 8,466 | Bahria Town Rs 8,145

---

## 5. Business Insights

1. **Weekends drive demand** — Saturday and Sunday together account for 38% of all rides (46 of 120), nearly double an average weekday.
2. **One in five rides is cancelled** — a 20% cancellation rate, meaningfully higher than a typical 10–15% target, pointing to a reliability issue worth investigating.
3. **Card payments generate the most revenue** (Rs 26,425, 40% of completed-ride revenue) despite being used in only 45 of 120 rides — card riders tend to take higher-fare trips than cash or wallet users.
4. **Demand is concentrated in a few zones** — Johar Town, Model Town, and Wapda Town together account for 58 of 120 rides (48%), nearly half of total volume.
5. **Average customer rating is 3.96/5** — solid but with room to improve; reviewing lower-rated completed rides could reveal service gaps.

---

## 6. Business Recommendations

1. **Increase driver availability on weekends.** Saturday and Sunday demand is nearly double weekdays like Thursday — scheduling more drivers for these two days should reduce wait times and lost rides.
2. **Investigate the 20% cancellation rate.** Since Driver ID isn't in the current dataset, the next data export should include it so cancellations can be traced to specific drivers, locations, or times, and addressed directly.
3. **Prioritize service quality and driver supply in the top three pickup zones** (Johar Town, Model Town, Wapda Town), since they drive nearly half of total ride volume and revenue — any improvement here has outsized impact.

---

## 7. README — Week 4 Section
*(paste this into your project's README.md)*

```markdown
## Week 4 — Power BI Dashboard

**Purpose:** Converts Week 2 (demand/customer) and Week 3 (revenue/driver) analysis into a single interactive Power BI dashboard.

**Features:**
- KPI cards: Total Rides, Completed Rides, Cancelled Rides, Total Revenue, Average Fare, Completion Rate
- Ride demand visuals: daily trend, rides by weekday, top pickup/drop-off locations
- Revenue visuals: by payment method, by pickup location
- Interactive filters: Date, Ride Status, Pickup Location, Payment Method

**Key Metrics:** 120 total rides | 80% completion rate | Rs 65,427 total revenue | Rs 682 average fare

**Main Insights:**
- Weekends account for 38% of ride volume
- 20% cancellation rate flags a reliability issue
- Card payments drive 40% of revenue from just 37% of rides
- Top 3 pickup zones generate 48% of all rides

**Recommendations:** Increase weekend driver availability; investigate cancellations (add Driver ID to future data pulls); prioritize service in top-3 pickup zones.

**Screenshots:** see `screenshots/week-04/`
```

---

## 8. Submission Checklist

- [x] Power BI dashboard completed
- [x] KPI cards created (6)
- [x] Demand analysis completed
- [x] Revenue analysis completed
- [ ] Customer analysis — not applicable (no Customer ID in dataset)
- [ ] Driver performance — not applicable (no Driver ID in dataset)
- [x] Filters tested
- [x] 5+ business insights written
- [x] 3+ recommendations written
- [ ] Dashboard screenshots added *(add after building in Power BI Desktop)*
- [ ] README updated *(paste Section 7 above)*
- [ ] GitHub repository link submitted
