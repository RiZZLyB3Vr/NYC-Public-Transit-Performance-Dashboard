### NYC Public Transit Performance Dashboard 🚌🚇
## 🚀 Introduction
Ever wondered which bus route in New York City is the most unreliable, or which subway station is the busiest? This project was born out of a curiosity to look under the hood of one of the world's most complex transit systems. Using real-world data from the NYC Open Data portal, I built an interactive Power BI dashboard to explore the performance of NYC buses and the ridership patterns of its iconic subway system for January and February 2024.

## 🎯 Project Goal
The primary objective was to develop a comprehensive Power BI dashboard to analyze and visualize two key aspects of the NYC transit system:

Bus Performance: To identify and quantify breakdowns and delays, pinpointing problematic routes and boroughs.

Subway Ridership: To understand passenger flow, identify the busiest stations, and analyze daily and weekly ridership trends.

## 📊 The Dashboard
The final product is a two-page interactive report that provides a holistic view of the transit system's performance.

Page 1: Subway Ridership Analysis
This page focuses on understanding passenger traffic.

Key Metrics: A high-level view of total subway ridership for the period.

Geospatial Analysis: A map visualizes all subway stations, with bubble sizes representing passenger volume, making it easy to spot the busiest hubs.

Trend Analysis: A daily trend line shows the fluctuations in ridership, revealing patterns across the week.

Leaderboards: Bar charts rank the top 10 busiest stations and subway lines.

Page 2: Bus Performance Analysis
This page is dedicated to operational efficiency and service reliability.

Key Metrics: KPI cards for the total number of incidents (breakdowns and delays) and the average delay duration in minutes.

Problem Hotspots: A treemap provides a clear breakdown of incidents by borough, while a bar chart identifies the top 10 worst-performing bus routes.

Trend Analysis: A line chart tracks the number of incidents per day, helping to identify problematic days or weeks.

Interactivity: The entire report is connected with slicers for Borough and Day of Week, allowing users to dynamically filter the data and drill down into specific areas of interest.

## 🛠️ Tools & Technologies
Microsoft Power BI

Power Query: For all data extraction, transformation, and loading (ETL).

DAX (Data Analysis Expressions): For creating custom measures and KPIs.

Data Modeling: For building a robust and efficient data model.

## ⚙️ The Process: From Raw Data to Insight
This project followed a structured, end-to-end business intelligence workflow.

1. Data Sourcing & Transformation (ETL)
I started by sourcing four distinct datasets from the NYC Open Data portal. In Power Query, I performed extensive cleaning and transformation. A key challenge was the How_Long_Delayed column in the bus data, which contained text ranges like "61-90 Min". I engineered a solution by splitting this column, extracting the lower and upper bounds, and calculating an average numerical value for analysis.

2. Data Modeling: The Star Schema
I built a star schema to create a robust and efficient data model. This involved a crucial problem-solving step:

Challenge: The initial relationship between the subway stations and ridership data was many-to-many, which broke the visuals and prevented proper filtering.

Solution: I diagnosed the issue—duplicate station IDs in the lookup table—and engineered a solution by creating a clean, unique dimension table (Dim_Subway_Stations). This resolved the cardinality issue and created a stable one-to-many relationship, a best practice in data modeling.

3. DAX for KPIs
I wrote several DAX measures to create the core metrics for the dashboard, such as Total Bus Incidents, Average Delay Minutes, and Total Subway Ridership.

## 💡 Challenges & Learnings
This project was a fantastic learning experience, full of real-world data challenges.

Messy Data is a Reality: The bus delay data taught me that raw data is rarely ready for analysis. The process of transforming text into a usable number was a practical lesson in the importance of ETL.

Data Modeling is Key: The many-to-many relationship issue was a critical roadblock. Solving it by creating a dedicated dimension table drove home the importance of a solid data model. A good model isn't just a technical step; it's the foundation of the entire report.

Pivoting is Part of Analysis: When I discovered the bus data couldn't be joined to individual stop locations, I pivoted the analysis to focus on routes and boroughs. This taught me that data analysis is often about adapting your approach to what the data allows.

Overall, this project solidified my end-to-end Power BI skills, from data cleaning and modeling to creating insightful and interactive visualizations.
