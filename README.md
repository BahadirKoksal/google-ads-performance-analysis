# 📊 Google Ads Performance Analysis — Google Sheets

## 🎯 Objective

This project analyzes annual Google Ads performance data for a Netflix marketing analytics scenario. The goal is to evaluate ad spend efficiency, calculate key performance metrics, identify the best-performing month, and provide actionable insights for the advertising director.

**Key Research Questions:**
- How much did we spend on Google Ads this year, and what did we get in return?
- What are our key performance metrics (CTR, CPC, CPM, ROAS, Conversion Rate)?
- Which month had the highest spend, conversions, and revenue?
- What drove December's outstanding performance?

---

## 📁 Dataset

**Source:** Instagram/Google Ads CSV data imported into Google Sheets  
**File:** `Yıl Sonu Reklam Performansı Analizi`  
**Period:** January – December 2023  
**Live Spreadsheet:** [View on Google Sheets](https://docs.google.com/spreadsheets/d/1sJc2MrZ_zfRWvI5YhrLvpkknNtit-SCO8YDt7pPShG4/edit)

### Raw Data Columns

| Column | Type | Description |
|---|---|---|
| `date` | DATE | Daily date |
| `impressions` | INTEGER | Number of times the ad was shown |
| `clicks` | INTEGER | Number of clicks on the ad |
| `spend` | CURRENCY | Amount spent on ads that day |
| `conversions` | INTEGER | Number of completed purchases/goals |
| `revenue` | CURRENCY | Revenue generated from conversions |

---

## 🗂️ Spreadsheet Structure

| Sheet | Description |
|---|---|
| `Google Ads Data` | Raw daily ad data imported from CSV |
| `google_metrikler` | Daily performance metrics calculated from raw data |
| `Pivot_table_monthly_analysis_google` | Pivot table aggregating data by month |
| `Monthly_Analysis_Google` | SUMIF-based monthly breakdown |
| `Özet_Google` | Summary dashboard with annual and monthly KPIs |

---

## 📸 Screenshots

### Raw Data
![Raw Data](screenshots/01_raw_data.png)

### Daily Metrics
![Daily Metrics](screenshots/02_daily_metrics.png)

### Pivot Table Monthly Analysis
![Pivot Table](screenshots/03_pivot_table.png)

### Monthly Analysis (SUMIF)
![Monthly Analysis](screenshots/04_monthly_analysis.png)

### Summary Dashboard
![Summary](screenshots/05_summary.png)

---

## 🔍 Analysis Steps

**1. Data Import & Cleaning**
Raw CSV data was imported into Google Sheets. Date column was verified and formatted correctly. Data was checked for missing values and formatting issues.

**2. Daily Metric Calculations (`google_metrikler` sheet)**
Six key advertising metrics were calculated for each day using Google Sheets formulas:

| Metric | Formula | Description |
|---|---|---|
| CTR | `=clicks / impressions` | Click-through rate — % of impressions that resulted in a click |
| Conversion Rate | `=conversions / clicks` | % of clicks that resulted in a conversion |
| CPM | `=spend / impressions * 1000` | Cost per 1,000 impressions |
| CPC | `=spend / clicks` | Cost per click |
| Avg. Conversion Value | `=revenue / conversions` | Average revenue per conversion |
| ROAS | `=revenue / spend` | Return on ad spend — revenue generated per £1 spent |

**3. Monthly Aggregation — Two Methods**

*Method 1: Pivot Table (`Pivot_table_monthly_analysis_google`)*
Used Google Sheets native Pivot Table feature to group data by month number (extracted via `MONTH()` function) and sum impressions, clicks, spend, conversions, and revenue. Custom calculated fields were added for Avg. Conversion Amount (`=revenue/conversions`) and ROAS (`=revenue/spend`).

*Method 2: SUMIF (`Monthly_Analysis_Google`)*
Used `MONTH()` to extract month numbers from dates, then `SUMIF()` to aggregate each metric by month manually — giving full control over the layout and formatting.

**4. Summary Dashboard (`Özet_Google`)**
Annual KPIs were calculated using `SUM()` and `AVERAGE()` functions referencing the metrics sheet. Monthly winner questions were answered using `MAX()` and `INDEX/MATCH` referencing the monthly analysis sheet.

---

## 📊 Key Results

### Annual Performance

| Metric | Value |
|---|---|
| Total Spend | £625,835.16 |
| Total Clicks | 418,914 |
| Total Impressions | 20,927,740 |
| Average CPC | £1.50 |
| Average CPM | £29.79 |
| Total Conversions | 7,763 |
| Avg. Cost per Conversion | £80.62 |
| Total Revenue | £1,211,548.17 |
| Annual ROAS | 1.94 |

### Monthly Winners

| Question | Answer |
|---|---|
| Highest spend month | December |
| Most conversions month | December |
| Highest revenue month | December |
| December CPC | £1.48 |
| December CPM | £30.22 |
| December avg. conversion value | £159.91 |

**Why December?** December is typically a strong month for e-commerce due to the Christmas season and holiday shopping — higher consumer intent drives more conversions at competitive ad costs.

---

## 🛠️ Google Sheets Functions Used

| Function | Purpose |
|---|---|
| `MONTH()` | Extract month number from date for grouping |
| `SUMIF()` | Sum metrics conditionally by month number |
| `SUM()` | Calculate annual totals |
| `AVERAGE()` | Calculate annual averages for CPC, CPM etc. |
| `MAX()` | Find the best-performing month value |
| `INDEX/MATCH` | Look up which month corresponds to the max value |
| Pivot Table | Drag-and-drop monthly aggregation with custom calculated fields |

---

## 🔧 Tools & Environment

- **Google Sheets** — All analysis, formulas, and pivot tables
- **Google Ads CSV Export** — Raw data source

---
