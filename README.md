# Blinkit Sales Analytics Dashboard

Interactive Power BI dashboard for comprehensive sales performance analysis

# 📌 Project Overview

The Blinkit Sales Analytics Dashboard is designed to deliver clear, actionable insight into sales performance across multiple dimensions—product categories, store sizes, customer ratings, time periods and more. Using Power BI, the solution empowers stakeholders to explore data, spot trends, and make data-driven strategic decisions with confidence.

# 🧩 Business Objectives

Provide an interactive self-service dashboard enabling end-users (business analysts, category leads, and senior management) to explore sales performance at granular and aggregated levels.

Visualise key performance indicators (KPIs) such as total sales, average sales per transaction, average customer ratings, and number of items sold.

Identify high- and low-performing segments (e.g., by product category or outlet size) and surface actionable insights for growth, optimization, and customer satisfaction.

Enable flexible slicing and dicing of data via dynamic filters so that users can drill into areas of interest (time-period, product category, outlet size, etc).

# 🛠 Dataset & Tools

Source: CSV (or XLSX) file titled Blinkit_Data_kaggle.xlsx (available in repo) containing sales, category, rating, outlet size and other relevant dimensions.

Tool: Power BI Desktop for ETL, modelling and visualisation; published to Power BI Service for sharing and collaboration.

Supporting files:

Blinkit_Sales_Dashboard.pbix (the Power BI report)

Blinkit_Sales_Report_Analysis.pdf (analytical summary / report)

Dashboard.pdf (dashboard snapshot)

# ✅ Methodology & Implementation

Data Loading & Initial Inspection

Loaded the dataset into Power BI Desktop.

In Power Query editor, enabled Column Distribution, Column Quality & Column Profile in View tab to identify missing values, value quality and distribution.

Data Cleaning & Transformation

Applied standard cleaning steps: removal of duplicates, handling nulls, standardising categorical values, type conversions, and possibly trimming whitespace.

Created any necessary derived columns or transformations to align with business logic.

Data Modelling & KPI Creation

Designed a metrics table using DAX to allow dynamic selection of KPIs via slicer.

Metrics =
{
  ("Total Sales", NAMEOF('BlinkIT Grocery Data'[Total Sales]), 0),
  ("Avg Sales", NAMEOF('BlinkIT Grocery Data'[Avg Sales]), 1),
  ("Avg Rating", NAMEOF('BlinkIT Grocery Data'[Avg Rating]), 2),
  ("No of Items", NAMEOF('BlinkIT Grocery Data'[No of Items]), 3)
}


<img width="484" height="164" alt="image" src="https://github.com/user-attachments/assets/298889d6-0ffb-4d8d-84d3-8c405fa05880" />

Created core measures for each selected KPI:

Total Sales = SUM('BlinkIT Grocery Data'[Sales])
Avg Sales   = AVERAGE('BlinkIT Grocery Data'[Sales])
Avg Rating  = AVERAGE('BlinkIT Grocery Data'[Rating])
No of Items = COUNTROWS('BlinkIT Grocery Data')

<img width="242" height="104" alt="image" src="https://github.com/user-attachments/assets/6bf34ecb-42f6-4aef-ac22-9f6828c9e513" />

<img width="248" height="105" alt="image" src="https://github.com/user-attachments/assets/1554ccd5-0dc6-4cc3-9deb-5654abd323d2" />

Linked those measures to card visuals, and designed slicer/matrix logic so that the user can switch the KPI context.

# Dashboard Construction

Developed a single-page interactive dashboard in Power BI Desktop:

Card visuals for high-level KPIs.

Bar/column charts to compare sales across categories and outlet sizes.

Filters/slicers for time (year, quarter), category, outlet size, rating band, etc.

Published the report to Power BI Service for sharing; configured user access/permissions accordingly.

Insights Extraction

Performed analytical review of the dashboard to surface key findings (see Insights section).

Documented findings in the Blinkit_Sales_Report_Analysis.pdf for stakeholders.

<img width="1355" height="773" alt="image" src="https://github.com/user-attachments/assets/5884e8c7-d6c3-4322-87a1-467c0415457d" />

📊 Key Insights at a Glance

Total Sales: ~ $1.20 M across the period under review.

Highest sales by product category: Fruits & Vegetables (~ $178.12 K)

Lowest sales by product category: Seafoods (~ $9.08 K)

Outlet size analysis: Medium-sized outlets lead (~ $507.9 K), high-size outlets lag (~ $248.99 K).

Average Ratings (by category):

Meat: 4.00/5

Household: 3.95

Baking Goods: 3.95

Canned: 3.95

Others (Health & Hygiene, Frozen Foods, Dairy, Seafood, Starchy Foods, etc.): ~3.91-3.93

Lowest rating observed: Breads ~3.83, Hard Drinks ~3.84

Additional observations:

A total of 8,523 items were sold across outlets and locations.

Items with “Low-Fat” content achieved higher sales (~ $776.32 K) compared to “Regular-Fat” (~ $425.36 K).

Sales peaked in 2018, which stands out as the highest-performing year in the dataset.

(Note: In calculating average ratings, null values were excluded to maintain integrity of the analysis.)

📁 Repository Structure
/Blinkit_Sales_Analytics_Dashboard/
│
├─ Blinkit_Data_kaggle.xlsx           ↳ Primary source dataset
├─ Blinkit_Sales_Dashboard.pbix        ↳ Power BI file (report and data model)
├─ Blinkit_Sales_Report_Analysis.pdf   ↳ Analytical summary of findings
├─ Dashboard.pdf                        ↳ Static snapshot of final dashboard
└─ README.md                            ↳ This document

# 🚀 How to Use the Dashboard

Clone or download the repository.

Open Blinkit_Sales_Dashboard.pbix in Power BI Desktop (version 2.XX or higher recommended).

Verify data source (the Excel file) is properly linked; refresh the data.

Browse the single-page report: use slicers to filter by product category, outlet size, year/quarter, fat-content, etc.

Explore each KPI card and related visuals to understand performance dynamics.

Export/print visuals as needed, or publish the report via Power BI Service for sharing with stakeholders.

# 🧠 Potential Next Steps

Extend the dashboard to include time-series forecasting (year/quarter) using built-in Power BI forecasting or Azure Machine Learning.

Introduce geospatial mapping if location data (zip/region) is available to analyse regional performance.

Add customer segmentation (e.g., loyalty status, frequency) to uncover patterns in repeat vs new customers.

Automate data refresh via Power BI Service and publish to a live workspace for real-time insights.

Enhance visuals with custom tooltips, drill-through pages and bookmarks to support deeper exploration.

# 📝 Authors & Contributors

Vibudh (aka VVRaider23) – Lead author of this analysis and dashboard development.

Feedback, improvements, or pull-requests are welcome. Please raise an issue or submit a PR.



