# 🏨 Hospitality Revenue Intelligence — AtliQ Hotels Case Study

<div align="center">

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Data Model](https://img.shields.io/badge/Data%20Model-Star%20Schema-6C3483?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-Hospitality%20Analytics-E74C3C?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-28a745?style=for-the-badge)

**Interactive Power BI dashboard tracking ₹1.69 Billion in hotel revenue across 4 Indian cities**  
*RevPAR · ADR · Occupancy · Booking Platform Mix · City-Level Performance*

[📊 View Dashboard](#dashboard) · [📐 Data Model](#data-model) · [🔍 Key Findings](#key-findings) · [💡 Business Insights](#business-insights) · [⚙️ Setup](#setup)

</div>

---

## 📌 Project Overview

AtliQ Hotels operates a chain of **luxury and business properties** across Delhi, Mumbai, Hyderabad, and Bangalore. This Power BI dashboard was built to give revenue managers a single view of performance across all properties, room types, booking platforms, and time periods — enabling faster, data-driven decisions.

**The core business problem:** Leadership had no centralized way to compare property performance, identify occupancy gaps, or understand which booking channels were most profitable.

**The solution:** A fully interactive, filter-driven dashboard with industry-standard hospitality KPIs built on a clean star schema data model.

---

## 📊 Dashboard

![AtliQ Hotels Dashboard](Hotels_Dashboard.png)

> **Filters available**: City · Room Type · Month (May–Jul) · Week Number  
> All KPIs update dynamically based on filter selection.

---

## 📐 Data Model

The dashboard is built on a **star schema** — the industry standard for BI reporting:

```
                    ┌─────────────┐
                    │  dim_date   │
                    │  (calendar) │
                    └──────┬──────┘
                           │
┌─────────────┐    ┌───────┴────────┐    ┌─────────────┐
│  dim_hotels │────│ fact_bookings  │────│  dim_rooms  │
│ (properties)│    │  (main fact)   │    │ (room types)│
└─────────────┘    └───────┬────────┘    └─────────────┘
                           │
               ┌───────────┴───────────┐
               │ fact_aggregated_      │
               │ bookings              │
               └───────────────────────┘
```

| Table | Type | Description |
|---|---|---|
| `dim_hotels` | Dimension | Property ID, name, city, category |
| `dim_rooms` | Dimension | Room class (Standard / Elite / Premium / Presidential) |
| `dim_date` | Dimension | Calendar table with week number, month |
| `fact_bookings` | Fact | Individual booking records with revenue, ratings, platform |
| `fact_aggregated_bookings` | Fact | Pre-aggregated bookings for performance metrics |

---

## 📈 Key Metrics (May–Jul Snapshot)

| KPI | Value | What It Means |
|---|---|---|
| **Total Revenue** | ₹1.69 Billion | Across all properties and room types |
| **RevPAR** | ₹7,256 | Revenue Per Available Room — core profitability KPI |
| **ADR** | ₹12,696 | Average Daily Rate — pricing efficiency |
| **Occupancy %** | 57.87% | Rooms filled vs. total available |
| **DSRN** | 2,556 | Daily Sellable Room Nights available |
| **Realization %** | 70.14% | Actual revenue vs. potential revenue |
| **Total Bookings** | 14,594 | Across all platforms |
| **Cancellation Rate** | 24.84% | Industry avg is ~20% — above benchmark |
| **Avg Rating** | 3.62 / 5 | Guest satisfaction score |

---

## 🔍 Key Findings

### 1. Luxury Leads Revenue, Business Leads Volume

| Category | Revenue |
|---|---|
| Luxury | ₹1,040M (61.5%) |
| Business | ₹648M (38.5%) |

Luxury properties generate significantly more revenue despite serving fewer guests — driven by higher ADR. However, Business properties offer more consistent occupancy.

---

### 2. Property Performance (All Cities)

| Property | City | Revenue | RevPAR | Occupancy | Realization | Avg Rating |
|---|---|---|---|---|---|---|
| Atliq Exotica | Mumbai | ₹117M | 503 | 57.87% | 70.39% | 4.32 ⭐ |
| Atliq Grands | Delhi | ₹86M | 153 | 57.87% | 70.01% | 4.25 ⭐ |
| Atliq City | Delhi | ₹54M | 233 | 57.87% | 71.20% | — |
| Atliq Palace | Delhi | ₹88M | 378 | 57.87% | 70.62% | 4.29 ⭐ |
| Atliq Seasons | Mumbai | ₹65M | 280 | 57.87% | 70.59% | 2.30 ⭐ |
| Atliq Grands | Hyderabad | ₹46M | 196 | 57.87% | 69.73% | 3.06 ⭐ |

> **Atliq Exotica Mumbai** is the top performer by revenue. **Atliq Seasons Mumbai** has the lowest guest rating (2.30) — an urgent quality signal.

---

### 3. Revenue by City

Mumbai leads all cities in revenue, followed by Bangalore, Hyderabad, and Delhi. Despite Delhi having the most properties, Mumbai's luxury tier drives higher yield per property.

---

### 4. Booking Platform Mix

| Platform | Bookings | Notes |
|---|---|---|
| LogTrip | Highest | Dominant OTA channel |
| Direct Online | Second | Lower commission cost |
| Others | Distributed | Makeyourtrip, Tripster, etc. |

Direct bookings are the most profitable channel (no OTA commission). LogTrip drives volume but at a cost margin impact.

---

### 5. Weekly Revenue Pattern

Revenue follows a **cyclical weekly pattern** — peaks at weeks 24, 27, and 29, with visible troughs in between. This suggests weekend-driven demand (leisure travel) alternating with lower mid-week corporate travel periods.

---

### 6. Cancellation Rate — The Hidden Problem

At **24.84%**, the cancellation rate exceeds the hospitality industry benchmark of ~20%. At ₹1.69B revenue, a 5% reduction in cancellations would recover approximately **₹84M in lost revenue**.

---

## 💡 Business Insights

### Revenue Strategy
- **Double down on Luxury in Mumbai** — highest RevPAR and revenue per property; prioritize investment here
- **Address Delhi underperformance** — multiple properties but lower revenue yield vs. Mumbai; pricing or positioning issue
- **Bangalore opportunity** — second-highest city revenue with fewer properties than Delhi; potential for expansion

### Platform & Channel Mix
- **Shift 5–10% of bookings from OTAs to direct** — each direct booking saves 15–20% in commission
- **Invest in LogTrip partnership** — dominant source of volume; negotiate preferred listing or dynamic pricing integration
- **Build direct loyalty program** — reduces OTA dependency and improves realization %

### Cancellation & Revenue Recovery
- **Implement non-refundable rate options** — discounted rates with stricter cancellation terms reduce cancellation risk
- **Atliq Seasons Mumbai (2.30 rating)** — investigate immediately; poor ratings drive higher cancellation rates and damage repeat bookings
- **Dynamic pricing on high-demand weeks** — weeks 24, 27, 29 show natural demand spikes; these are yield management opportunities

### Occupancy Optimization
- **57.87% occupancy is below the luxury benchmark of 65–70%** — targeted corporate tie-ups or event-based promotions can close this gap
- **DSRN of 2,556** — with realization at 70.14%, approximately 750 room nights per day are going unrealized

---

## 📁 Repository Structure

```
Hotels-Data-analysis-Powerbi-dashboard/
│
├── dashboard.pbix                  # Power BI source file (fully interactive)
├── Hotels_Dashboard.png            # Dashboard screenshot
├── filter.png                      # Filter panel screenshot
│
├── dim_date.csv                    # Calendar dimension
├── dim_hotels.csv                  # Property master data
├── dim_rooms.csv                   # Room type dimension
├── fact_bookings.csv               # Individual booking transactions
└── fact_aggregated_bookings.csv    # Aggregated booking metrics
```

---

## ⚙️ Setup

**Requirements**: Power BI Desktop (free — [download here](https://powerbi.microsoft.com/desktop/))

```bash
# Clone the repo
git clone https://github.com/haseeb774/Hotels-Data-analysis-Powerbi-dashboard.git
```

1. Open `dashboard.pbix` in Power BI Desktop
2. All data is pre-loaded from the CSV files — no database connection needed
3. Use the slicers (City, Room Type, Month, Week) to explore the dashboard interactively

---

## 🏨 About the Dataset

This project uses a **hospitality domain dataset** modeled after real hotel chain operations. The data includes:
- 14,594 booking records across May–July
- 7 properties across 4 Indian cities
- 4 room categories: Standard, Elite, Premium, Presidential
- 6+ booking platforms including OTAs and direct channels

---

## 👤 Author

**Haseeb ur Rehman**  
Data Analyst · Power BI · SQL · Python

[![GitHub](https://img.shields.io/badge/GitHub-haseeb774-181717?style=flat&logo=github)](https://github.com/haseeb774)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://linkedin.com/in/haseeb-u-rehman-4822bb369)

---

<div align="center">
<i>If this project was useful to you, consider leaving a ⭐</i>
</div>