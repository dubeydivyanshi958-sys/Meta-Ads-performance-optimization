
# Pinnacle Meta Ads Campaign Dataset – Marketing Analytics & Performance Optimization (EDA)

## Project Overview
This project focuses on cleaning, transforming, and analyzing a Meta Ads campaign dataset containing:

- 10,000+ rows (Ads)  
- ~50 structured columns (after preprocessing)  
- Embedded JSON targeting specifications  
- Campaign, Ad Set, and Ad-level performance metrics  

The dataset required preprocessing due to:

- Semi-structured JSON columns  
- Redundant system-generated metrics  
- Hourly and weekday breakdown columns  
- High null-value fields  
- Mixed data types  

The primary objective was to prepare the dataset in Excel and perform advanced Exploratory Data Analysis (EDA) in Python to generate actionable marketing insights.

---

## Phase 1: Excel Data Cleaning & Structuring

### JSON Column Handling
- Extracted targeting information (age range, interests, behaviors, geo-location).  
- Removed raw nested JSON columns after flattening key fields.  
- Reduced structural complexity for analytical clarity.  

### Data Standardization
- Converted dates, currency, and numeric fields to appropriate formats.  
- Ensured Ad ID uniqueness.  
- Cleaned text-based NaN values to avoid Python parsing issues.  

### Column Reduction & Optimization
- Removed columns with 80–90% null values.  
- Dropped hourly breakdown columns (recalculable in Python).  
- Deleted weekday-specific columns (can be derived from date).  
- Removed derivable metrics such as Ad Rank, Top 25% CPC etc.  
- Focused dataset on core KPIs.  

### Feature Engineering
Created new calculated metrics:  
- Engagement Rate (24hr, 7-day, overall)  
- Conversion Rate (24hr, 7-day, overall)  
- Monthly performance column  
- Date range & time-based derived columns  

### Excel Pivot Analysis
Performed structured pivot summaries for:  
- Platform-Level Analysis (Spend, Conversions, CPC, Conversion Rate)  
- Campaign-Level Performance (Payments, CPLPV, ROI %, CTR %)  
- Daily Performance Summary (Day-wise payments, CPC trends, Conversion trends)  

---

## Phase 2: Python-Based EDA

### Libraries Used
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  

### Analysis Performed
- KPI recalculation validation  
- Null and anomaly checks  
- Distribution analysis  
- Platform comparison  
- Campaign efficiency benchmarking  
- Correlation analysis  
- Outlier detection  

---

## Final Insights & Optimization Decisions

### Ad-Level Performance
Out of 237 Ads:  
- 24 Ads meet performance benchmarks (High CTR + Low CPC + Strong Conversion Rate)  
- 183 Ads paused (Below target benchmark performance)  
- 30 Ads recommended for discontinuation (Low CTR, High CPC, Poor Conversion)  

**Platform Performance (Winning Platform):**  
- Facebook: 6 Ads  
- Instagram: 7 Ads  
- Threads: 11 Ads  
Threads emerged as the strongest performing platform.  

**Best Day to Run Ads:**  
- Tuesday: 308 Payments, Lowest CPC ₹3.5, Above-average conversion rate  
Recommendation: Increase budget allocation on Tuesdays.  

---

### Campaign-Level Insights
- **Best Performing Campaign:**  
  "VM || Delhi NCR || Traffic"  
  - Lowest CPC: ₹1.16  
  - Highest Payments: 568  
  - Conversion Rate: 0.77  
  Recommended to continue & scale.  

- **Needs Optimization:**  
  "Web App | Conversion"  
  - Highest Spend: ₹181K+  
  - High CPC: ₹13.26  
  - Low Conversion Rate: 0.37  
  Requires targeting and cost optimization.  

- **Awareness Campaign Analysis:**  
  "VM Brand Awareness"  
  - 8.79% of total spend  
  - CTR: ₹0.08 (very cost-efficient)  
  - Poor in direct conversions  
  Effective for reach, not for payment conversion.  

- **Least Performing Campaigns (Discontinue):**  
  "ToF Engagement" and "Straight Outta"  
  - 0 Payments  
  - Consumed budget  

---

### Ad Set-Level Insights
- **Top Performing Ad Set:**  
  "Women - Clubbed Audience"  
  - 567 Payments  
  - Lowest CPLPV: ₹2.30  
  - Conversion Rate: 0.81  
  Recommended to scale.  

- **Strong Efficiency:**  
  "RMK - Waitlist"  
  - Conversion Rate: 1.05  
  - CPLPV: ₹18.50  
  Maintain & optimize budget.  

- **Underperforming Ad Sets (Discontinue):**  
  - Dating Apps  
  - Entrepreneurship Insta  
  - Travel Insta  
  - Interest-Based Dinner  

---

### Top Performing Ads
- **Top 5 Ads (High Spend % + High Payments):**  
  - Monkey UGC  
  - Ad – 1 (5 Strangers)  
  - Saturday Night  
  - Ranveer  
  - Instagram Post – Latest StepOut Dinner  

- **Top 3 Ads (Most Efficient):**  
  - Monkey UGC  
  - Saturday Night  
  - Ranveer  
Metrics: High Payments, CPLPV below ₹1.5, Conversion Rate ~0.70  
Recommended for scaling.  

---

## Tech Stack
- Microsoft Excel (Cleaning + Pivot Analysis)  
- Python (Pandas, NumPy)  
- Matplotlib & Seaborn  
- Git & GitHub  

---

## Project Value
This project demonstrates:  
- Handling of semi-structured marketing export data  
- JSON-based targeting interpretation  
- KPI modeling & performance benchmarking  
- Campaign optimization strategy development  
- Data-driven decision making for ad scaling or discontinuation  

---

## KPI & Metric Formulas Used

### Core Performance Metrics
- CTR (%) = (Clicks / Impressions) × 100  
- CPC = Total Spend / Total Clicks  
- Conversion Rate = Conversions / Clicks  
- CPA = Total Spend / Total Conversions  
- CPLPV = Total Spend / Landing Page Views  
- Engagement Rate = Total Engagements / Impressions  
- ROI (%) = ((Revenue – Spend) / Spend) × 100  

### Time-Based Metrics
- Daily Impressions = SUM(Impressions grouped by Date)  
- Daily Conversions = SUM(Conversions grouped by Date)  
- Daily CPC = Daily Spend / Daily Clicks  
- Monthly Spend = SUM(Spend grouped by Month)  
- Monthly Conversion Rate = Monthly Conversions / Monthly Clicks  

### Benchmark Comparison
- Performance vs Group Average: Ad Metric / Group Average Metric  
- Performance vs Top 25 Percentile: Ad Metric / Top 25% Benchmark  

### Decision Threshold Logic
- Continue: CTR above average, CPC below average, Conversion Rate above benchmark  
- Pause: CTR near average, Moderate CPC, Inconsistent conversions  
- Discontinue: Conversion Rate < 0.01, High CPA, Zero payments despite spend  

