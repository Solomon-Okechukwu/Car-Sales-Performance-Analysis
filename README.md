**# Car-Sales-Performance-Analysis**
---
## Table of Contents
---
- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaningpreparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#resultsfindings)
- [Recommendation](#recommendation)
- [Dashboard Preview](#dashboard-preview)
- [Limitations](#limitations)
- [References](#references)
  
## Project Overview
This project analyzes Auto Style Limited’s 2020 car sales data to support the company’s plan to open a new branch. Using Power BI, I cleaned and visualized the data to identify the most profitable location, understand customer demographics, highlight top-selling car brands and models, and reveal seasonal sales trends. The insights guided recommendations on where, what, and when to expand for maximum business impact
Power BI project analyzing Auto Style Limited's 2020 car sales data to identify the best location, product lineup, target customers, and timing for a new branch expansion

## Objectives
- Identify the region with the highest untapped market potential.
- Understand which car brands/models are in highest demand.
- Analyze customer demographics (age, gender, region).
- Identify peak sales periods and seasonal trends.

## Data Source
The dataset for this project contains car sales transactions from Auto Style Limited for the year 2020.  
It was used to analyze sales performance, identify trends, and recommend the best location for a new branch expansion.
[Download Raw Dataset](https://github.com/Solomon-Okechukwu/Car-Sales-Performance-Analysis/blob/main/AutoStyle_Sales_2020_Raw_data.xlsx)
[Download Cleaned Dataset](https://github.com/Solomon-Okechukwu/Car-Sales-Performance-Analysis/blob/main/AutoStyle_Sales_2020_Cleaned_data.xlsx)

## Tools
- Power BI (including Power Query Editor) – for data cleaning, modeling, and visualization [Download_Power_BI](https://powerbi.microsoft.com/)  
- Microsoft Excel – for dataset storage and initial format inspection [Download_Microsoft_Excel](https://www.microsoft.com/microsoft-365/excel) 
- GitHub – for project documentation and sharing [Download_GitHub](https://github.com/)

## Data Cleaning/Preparation
Data was cleaned and prepared in Power Query Editor (inside Power BI) before visualization.  
The main steps included:
- Promoted headers to ensure first row was recognized as column titles.
- Changed data types (e.g., Sales Date → Date, Sales Amount → Decimal Number).
- Removed duplicates based on Transaction ID to avoid double-counting.
- Standardized text values (e.g., "lagos" → "Lagos", "toyota" → "Toyota").
- Handled missing values by replacing blanks in the Age column with the median age.
- Corrected inconsistent categorical values & typos** (e.g., "malee" → "Male", "FEMALE" → "Female").
- Removed outliers by filtering unrealistic ages (<18 and >50).
- Created new columns:
  - Age Range – Grouped customers into categories (18–25, 26–35, etc.).
  - Month-Year – Extracted from Sales Date for sales trend analysis.
- Renamed columns for consistency and readability (e.g., "Cust_ID" → "Customer ID").

## Exploratory Data Analysis
EDA involves exploring the sales data to answer key business questions such as:
- Analyze sales performance across existing branches
- identify regions with high untapped market potentials
- understand which car brands/models are in the highest demand
- recommend opportunities to expand popular products into new markets
- analyze customer age, gender, and region to uncover key demographic trends
- identify peak sales period and seasonal trends in 2020
- use trends to forcast future performance and inform expansion timing

## Data Analysis
Performed calculations in Power BI using DAX and Conditional Columns to generate insights and create filters for the dashboard.
- Outlier Detection(Unit Sales): Unit Q1 = PERCENTILE.INC(Sales[Unit], 0.25)
  Unit Q3 = PERCENTILE.INC(Sales[Unit], 0.75)
  Unit IQR = [Unit Q3] - [Unit Q1]
Is Outlier =
  IF(
    Sales[Unit] < ([Unit Q1] - 1.5 * [Unit IQR]) ||
    Sales[Unit] > ([Unit Q3] + 1.5 * [Unit IQR]),
    "Yes", "No"
    )
- Age Outlier Removal (Conditional Column): If Age < 14 then "Yes"
  Else if Age > 54 then "Yes"
  Else "No"
- Age Range Grouping (Conditional Column): If Age >= 20 and Age <= 24 then "20-24"
  Else if Age >= 25 and Age <= 29 then "25-29"
  Else if Age >= 30 and Age <= 34 then "30-34"...

## Results/Findings
The results of the analysis are summarized as follows:
  
#### Customer Demographics
- Age Range: Majority of customers are between 26–40 years (84% of sales), with 26–30 (480 sales) and 31–35 (457 sales) as the top groups.
- Gender: Sales are balanced across genders – female (51%), male (49%).
  
#### Sales Trends
- Monthly: Sales grew steadily from Jan–May, dipped in June, then peaked in November (200 sales) before dropping in December (61 sales).
- Quarterly: Sales were lowest in Q1 and highest in Q3–Q4, indicating stronger performance in the second half of the year.
  
#### Location Performance
- Top Branch: Lagos recorded the highest sales (361 units).
- Lowest Branch: Ekiti had only 17 sales.
- Observation: Approximately 99% of sales came from 5 branches, showing uneven distribution.
  
#### Product Performance
- Car Models: Corolla leads with 201 units, while Passat and Highlander had only 3 units each.
- Car Brands: Ford (368 sales) and Toyota dominate, with Honda, Nissan, and Hyundai also strong. Together, the top 5 brands contribute approximately 90% of sales.

## Dashboard Preview
  Here is an overview of the Car Sales Performance Dashboard
  ![Dashboard Overview](Car%20Sales%20Dashboard.PNG)

## Recommendation
  - Target expansion in urban regions with high untapped demand (e.g., Northern Nigeria).
- Prioritize stocking high-demand models (Corolla, Camry, Ford SUVs) in the new branch.
- Align campaigns with Q3–Q4 sales peak (festive season).
- Focus marketing on customers aged 26–40 while maintaining balanced gender messaging.

## Limitations
During the analysis, several data quality issues were identified and addressed:
- Outliers: Extreme sales values were removed to avoid skewing the results.
- Age Range: Customer ages were grouped into categories (e.g., 21–25, 26–30, 31–35, etc.) to simplify demographic analysis.
- Inconsistencies in Entries:
  Corrected spelling errors such as “malee” → “male”.
- Missing Data: Records with incomplete or missing key information were excluded from the analysis.
  Limitations:
- Cleaning decisions (like removing outliers) may slightly affect total sales figures.
- Grouping ages into ranges can hide small variations within age brackets.
- Limited dataset (2020 only) may not fully represent long-term sales trends.

## References
- Dataset source: Skill Ahead – Free Dataset Storage Folder (2020).  
- Guidance from personal Power BI training notes and documentation.

😄
💻
📊

|Heading1|Heading2|
|--------|--------|
|Content1|Content2|
|Excel|Power BI|

