# IOCL_BI_Project
An interactive Power BI dashboard analyzing 5 years (2018–2023) of Indian Oil Corporation (IOCL) stock market data, featuring advanced DAX calculations, Star Schema data modeling, dynamic metric selection, stock price trends, trading volume, liquidity analysis, and market volatility insights.
# Indian Oil Corporation (IOCL) – Stock Market Analysis Dashboard | Power BI

## Project Overview

Developed an interactive Power BI dashboard to analyze the historical stock market performance of **Indian Oil Corporation Limited (IOCL)** using approximately five years of historical trading data (2018–2023).

The project focuses on financial data modeling, advanced DAX calculations, stock price movements, trading volume patterns, liquidity analysis, and market volatility. It transforms raw historical stock market data into meaningful financial insights through interactive visualizations and dynamic analytical capabilities.

## Dataset Overview

- **Company:** Indian Oil Corporation Limited (IOCL)
- **Analysis Period:** July 30, 2018 – July 27, 2023
- **Trading Sessions:** 1,233
- **Historical Price Range:** ₹47.70 – ₹113.13
- **Average Daily Trading Volume:** 21.83 Million Shares
- **Total Traded Value:** ₹2.03 Trillion

## Key Technical Implementations

### 1. Data Modeling & Power BI Architecture
- Designed a Star Schema data model to organize financial data and improve analytical structure.
- Created a custom Date Dimension (`Dim_Date`) to support time-based analysis.
- Established relationships between the date dimension and historical stock transactions.
- Structured the model to support year, quarter, and month-level analysis.

### 2. Advanced DAX & Dynamic Analytics
- Developed custom DAX measures to calculate stock performance indicators, daily price volatility, and trading turnover.
- Calculated average intraday high-to-low price variation of approximately 2.72%.
- Analyzed cumulative traded value exceeding ₹2.03 trillion.
- Implemented disconnected parameter tables to enable dynamic metric selection within a single visual.
- Created interactive measures and calculations to support flexible financial analysis.

### 3. Interactive Analysis & Visualization
- Implemented drill-down functionality across yearly, quarterly, and monthly hierarchies.
- Used Decomposition Trees to investigate the factors contributing to trading turnover.
- Developed dynamic visualizations for stock price movements, trading volume, and financial performance.
- Incorporated volume-tier segmentation to compare trading activity across different volume categories.

## Key Business & Financial Insights

### Stock Price Performance
- Identified the historical closing price peak of ₹113.13 in May 2019 and the lowest observed price of ₹47.70 in March 2020.
- Observed a decline in annual average closing price to ₹60.05 in 2020, followed by a recovery to ₹72.46 in 2021, ₹75.55 in 2022, and ₹84.57 in 2023 (through July).
- Analyzed the stock's price trajectory to understand its multi-year recovery pattern.

### Liquidity & Trading Volume Analysis
- Identified an average daily trading volume of approximately 21.83 million shares.
- Recorded a maximum single-day trading volume of 314.89 million shares.
- Observed elevated trading activity in 2020 and 2021, with annual trading volumes exceeding 7.74 billion and 6.74 billion shares, respectively.
- Discovered that trading sessions with volumes exceeding 30 million shares represented approximately 19% of trading days but contributed nearly 41% of total traded value.
- Used volume-tier segmentation to examine the relationship between trading activity and market turnover.

### Volatility Analysis
- Calculated an average intraday high-to-low price variation of approximately 2.72%.
- Examined daily price ranges to identify periods of relatively higher and lower price fluctuations.
- Used historical price and volume patterns to understand changes in market activity over the analysis period.

## Tools & Technologies

- **Power BI Desktop:** Dashboard development and interactive reporting
- **DAX:** Financial calculations, custom measures, and dynamic metric selection
- **Data Modeling:** Star Schema and Date Dimension
- **Power BI Features:** Decomposition Tree, Drill-Down, Interactive Slicers, Disconnected Parameter Tables

## Project Objective

The objective of this project was to demonstrate how Power BI, financial data modeling, and advanced DAX can be used to transform historical stock market data into an interactive analytical solution, enabling users to explore stock performance, liquidity patterns, trading activity, and price movements.

## DAX Implementation

This project uses DAX calculated tables and measures
to support financial analysis and interactive reporting.

- [DAX Calculated Tables](DAX_Tables.md)
- [DAX Measures](DAX_Measures.md)
