# HR Analytics & Workforce Attrition Executive Dashboard

An interactive, data-driven HR Analytics dashboard built in Microsoft Excel using Power Query, Power Pivot (DAX), and custom Pivot Chart Staging Areas. 

This project explores workforce attrition patterns across key employee dimensions (Department, Job Role, Overtime Status, and Tenure) to deliver actionable retention strategies for leadership.

---

## Executive Dashboard Preview

![Executive Dashboard](dashboard_screenshot.png)
---

## Business Problem & Objectives

High employee attrition increases recruitment costs and impacts organizational performance. The primary objective of this project is to analyze workforce turnover drivers and provide data-backed recommendations to reduce turnover.

**Key Metrics Tracked:**
* **Total Headcount:** Total active and past workforce size.
* **Attrition Count:** Total number of employees who have left the organization.
* **Attrition Rate (%):** Percentage of total workforce lost to turnover.

---

## Tech Stack & Methodology

| Tool / Technology | Purpose |
| :--- | :--- |
| **Power Query** | Data ingestion, data cleaning, date parsing, and column transformations (`Attrition Flag`). |
| **Power Pivot & DAX** | Built relational Data Model and performance metrics using dynamic DAX measures. |
| **Excel Staging Tables** | Designed structured Pivot Table backends for clean chart mapping. |
| **Interactive Dashboard** | Formatted KPI scorecard, custom visual palettes, and dynamic global slicers. |

---

## Data Modeling (DAX Measures)

The following explicit DAX measures were created in Power Pivot to drive the analysis:

```dax
-- Total Workforce Headcount
Total Headcount := COUNTROWS(tbl_HR_Analytics)

-- Total Attrition Count
Attrition Count := CALCULATE([Total Headcount], tbl_HR_Analytics[Attrition Flag] = 1)

-- Attrition Rate (%)
Attrition Rate (%) := DIVIDE([Attrition Count], [Total Headcount], 0)
```
---
## Key Business Insights
Overtime Impact: Employees working overtime experience significantly higher turnover (~30.5%) compared to non-overtime staff (~10.4%).

High-Risk Job Roles: Sales Representatives (39.76%) and Laboratory Technicians (23.94%) show the highest attrition rates across the organization.

Tenure Distribution: Attrition peaks heavily during the initial employee onboarding phase (<1 Year tenure cohort at ~31.6%).

## Strategic Recommendations
Capacity & Workload Planning: Audit workload distribution in high-overtime departments to mitigate burnout.

Targeted Role Retention: Re-evaluate compensation structures, career growth pathways, and day-to-day conditions for Sales Representatives and Laboratory Technicians.

Onboarding Optimization: Strengthen 30-60-90 day onboarding and mentorship programs to improve early-tenure retention.
