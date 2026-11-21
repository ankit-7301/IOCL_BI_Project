# DAX Calculated Tables – IOCL Stock Market Analysis

This document contains the three calculated tables developed using DAX in the IOCL Stock Market Analysis Power BI project. These tables support dynamic metric selection, time intelligence, and stock price volatility segmentation.

## 1. Dimension Table – Stock Metrics (`dim_stock_metrics`)

**Purpose:** Created a disconnected parameter table to enable dynamic metric selection within Power BI visuals.

**DAX Code:**

```dax
dim_stock_metrics =
DATATABLE(
    "MetricID", INTEGER,
    "MetricName", STRING,
    {
        {1, "closing price"},
        {2, "Traded Volume"},
        {3, "Daily turnover"},
        {4, "Intraday range %"}
    }
)
```

**Key Implementation:**
- Created a static table using `DATATABLE()`.
- Defined four analytical metrics with unique Metric IDs.
- Used as a disconnected table to allow users to switch between different stock market metrics dynamically.
- Supports interactive dashboard analysis through slicers and DAX SWITCH logic.

## 2. Date Dimension Table (`dim_table`)

**Purpose:** Developed a custom Date Dimension to support time-based financial analysis and establish a structured Star Schema data model.

**DAX Code:**

```dax
dim_table =
VAR MinDate = MIN('Indian Oil Data (2)'[Date])
VAR MaxDate = MAX('Indian Oil Data (2)'[Date])
RETURN
ADDCOLUMNS(
    CALENDAR(MinDate, MaxDate),
    "year", YEAR([Date]),
    "YearMonth", FORMAT([Date], "YYYY-MM"),
    "Month No", MONTH([Date]),
    "Month Name", FORMAT([Date], "MMMM"),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "DayoFWeek", FORMAT([Date], "dddd"),
    "DayoFWeekNumber", WEEKDAY([Date], 2),
    "IsWeekend",
        IF(
            WEEKDAY([Date], 2) IN {6, 7},
            "Weekend",
            "Trading Day"
        )
)
```

**Key Implementation:**
- Generated a dynamic date range using the minimum and maximum transaction dates.
- Created Year, Year-Month, Month Number, Month Name, and Quarter attributes.
- Added weekday names and weekday numbers for time-based analysis.
- Classified dates into weekends and trading days.
- Used as the Date Dimension in the Star Schema model for date-based analysis and drill-down functionality.

## 3. Price Volatility Group Table (`price_volatility_group`)

**Purpose:** Created a volatility classification table to categorize stock trading sessions based on their intraday price spread.

**DAX Code:**

```dax
price_volatility_group =
DATATABLE(
    "volatility Tier", STRING,
    "MinSpreadpct", DOUBLE,
    "MaxSpreadpct", DOUBLE,
    "SortOrder", INTEGER,
    {
        {"Low volatility (<1.5%)", 0.0, 0.015, 1},
        {"Moderate volatility (1.5%-3%)", 0.015, 0.030, 2},
        {"High Volatility (3%-5%)", 0.030, 0.050, 3},
        {"Extreme volatility (>5%)", 0.050, 1.0, 4}
    }
)
```

**Key Implementation:**
- Defined four volatility categories using predefined percentage thresholds.
- Used minimum and maximum spread percentages to classify trading sessions.
- Added SortOrder to maintain the correct sequence of volatility categories in Power BI visuals.
- Supports volatility segmentation and comparative analysis across different market conditions.

## Summary of DAX Implementation

| Calculated Table | Primary Purpose |
|---|---|
| dim_stock_metrics | Dynamic metric selection |
| dim_table | Date dimension and time intelligence |
| price_volatility_group | Intraday volatility classification |

**Power BI Concepts Demonstrated:** DAX Calculated Tables, DATATABLE(), ADDCOLUMNS(), CALENDAR(), Time Intelligence, Disconnected Tables, Financial Data Modeling, and Data Segmentation.
