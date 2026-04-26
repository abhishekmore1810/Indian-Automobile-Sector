# Indian Automobile Sector

# Project Overview

This project focuses on analyzing the Indian automobile sector using Excel, SQL Server, and Power BI. The goal was to clean, transform, and integrate automobile related datasets from multiple sources and create an interactive dashboard for business insights.

The dashboard helps understand:

- Total number of cars
- Total sales value
- Brand distribution
- Fuel type analysis
- Model-wise car distribution
- Manual vs Automatic transmission analysis
- Year-wise sales performance

This project demonstrates the complete Data Analytics workflow from raw data preparation to business intelligence dashboard creation.

# Objective

The main objective of this project is to analyze automobile sales and operational data to identify market trends, customer preferences, and business opportunities in the Indian automobile sector.

The dashboard helps stakeholders make data driven decisions regarding:

- Sales strategy
- Inventory planning
- Fuel type demand
- Brand performance
- Transmission preferences
- Market growth trends

# Solution

To solve this problem:

- Multiple datasets were cleaned and standardized using Excel
- Data was integrated using SQL Server with joins
- A master table was created for centralized analysis
- Power BI dashboard was developed for interactive reporting

This solution provides a single source of truth for better decision-making and business growth.

# Tools Used
- Excel → Data Cleaning & CSV Conversion
- SQL Server Management Studio (SSMS) → Data Integration & Querying
- Power BI → Dashboard Development & Visualization

# Step 1: Excel Data Preparation
# Tasks Performed
# 1. Data Cleaning

The raw Excel files were checked for:

- Duplicate records
- Blank/null cells
- Incorrect values
- Data consistency issues

This ensured high-quality and reliable data for analysis.

# 2. Validate Column Formats

Column data types were verified such as:

- Numeric columns
- Date columns
- Text fields
- IDs and keys

This avoided import and relationship issues later.

# 3. Convert Excel Files to CSV

After cleaning, all Excel sheets were converted into CSV format for easy import into SQL Server.



# Step 2: SQL Server Data Integration
# Tasks Performed
# 1. Create Database

A new database named Car was created.

CREATE DATABASE Car;

USE Car;

# 2. Import CSV Files into SQL Server

The following CSV files were imported into SQL Server:

- Car
- Insurance
- Owners
- Sales
- Service_History

Each file was stored as an individual table.

# 3. Create Master Table Using LEFT JOIN

Since Car_ID is common across all tables, it was used to join the datasets and create a centralized master table.

# SQL Query

--Join the tables and create one Master Table

  SELECT 
      Car.[Car_ID],
      [Brand],
      [Model],
      [Year],
      [Fuel_Type],
      [Transmission],
      [Color],
      [Owner_Type],
      [Mileage_kmpl],
      [Price_Lakh],
      [Provider],
      [Policy_Number],
      [Expiry_Date],
      [Status],
      [Owner_Name],
      [Contact],
      [City],
      [Purchase_Year],
      [Sale_Price_Lakh],
      [Sale_Date],
      [Buyer_Name],
      [Service_Type],
      [Service_Date],
      [Service_Cost],
      [Service_Center]

INTO MASTER_CARD_DATA

FROM Car

LEFT JOIN Insurance
ON Car.Car_ID = Insurance.Car_ID

LEFT JOIN Owners
ON Owners.Car_ID = Car.Car_ID

LEFT JOIN Sales
ON Sales.Car_ID = Car.Car_ID

LEFT JOIN Service_History
ON Service_History.Car_ID = Car.Car_ID;

This created a unified dataset for dashboard development.

# Step 3: Power BI Dashboard Development
# Tasks Performed
# 1. Connect SQL Server to Power BI

The SQL Server database was connected directly to Power BI for live data access.

# 2. Project Title

A text box was added with the title:

Indian Automobile Sector

# 3. KPI Cards Created

The following KPIs were developed:

- Total Cars → 50.00K
- Total Sale Price → 1.30M
- Total Brand → 10
- Total Fuel Type → 5
- Total Model → 10

These KPIs provide quick high-level insights.

# 4. Car by Fuel Type (Stacked Bar Chart)

Used:

- Fuel Type
- Distinct Count of Car_ID

Purpose:

To identify which fuel type is most popular among customers.

# 5. Sales by Year (Stacked Column Chart)

Used:

- Sales Year
- Sale Price in Lakh

Purpose:

To analyze yearly sales trends and revenue growth.

# 6. Car by Model (Donut Chart)

Used:

- Car Model
- Distinct Count of Car_ID

Purpose:

To compare model-wise car distribution.

# 7. Manual vs Automatic (Pie Chart)

Used:

- Transmission Type
- Distinct Count of Car_ID

Purpose:

To understand customer preference between manual and automatic cars.

# 8. Final Dashboard Design

The dashboard was formatted with:

- Professional layout
- Clean design
- Consistent color theme
- Easy navigation
- Business-friendly visualization structure

This improved usability and presentation quality.

# Dashboard Insights
# Key Findings
# 1. Diesel Cars Have the Highest Count

Diesel vehicles slightly lead compared to Electric, CNG, Hybrid, and Petrol vehicles.

This indicates strong diesel market demand.

# 2. Sales Performance is Highest in 2022 and 2023

Sales remained strong in 2022 and 2023, while 2024 shows significantly lower values, indicating either incomplete data or market decline.

# 3. Manual and Automatic Preference is Nearly Equal

The split is almost 50-50, showing balanced customer demand for both transmission types.

# 4. Car Models Are Evenly Distributed

No single model dominates the market significantly, indicating diversified customer choices.


# Business Recommendations

# 1. Focus More on High-Demand Fuel Types
Increase inventory and marketing for Diesel and Electric vehicles.

# 2. Improve 2024 Sales Performance
Investigate the cause of low 2024 sales and optimize pricing and promotions.

# 3. Balanced Transmission Strategy
Since both Manual and Automatic are equally preferred, maintain balanced stock availability.

# 4. Model-Level Promotion
Promote underperforming models using offers and targeted campaigns.

# Conclusion

This project successfully transformed raw automobile data into meaningful business insights using:

Excel + SQL + Power BI

It demonstrates strong skills in:

- Data Cleaning
- SQL Query Writing
- Data Modeling
- Dashboard Design
- Business Analysis
- Insight Generation
