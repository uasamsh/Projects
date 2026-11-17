# DAX Measures – Super Store Dashboard

Create these as **New measure** in the `Orders` table (Modeling > New measure).
The current report uses raw columns summed automatically; named measures are cleaner and reusable.

> **Columns verified** against `data/Sample_Superstore.xlsx` (sheet `Orders`): `Order ID`, `Order Date`, `Ship Date`, `Ship Mode`, `Customer ID`, `Customer Name`, `Segment`, `Country/Region`, `City`, `State`, `Postal Code`, `Region`, `Product ID`, `Category`, `Sub-Category`, `Product Name`, `Sales`, `Quantity`, `Discount`, `Profit`. The measures below use these exact names.

## Core KPIs
```DAX
Total Sales = SUM ( Orders[Sales] )

Total Profit = SUM ( Orders[Profit] )

Total Quantity = SUM ( Orders[Quantity] )

Avg Discount % = AVERAGE ( Orders[Discount] )

Profit Margin % = DIVIDE ( [Total Profit], [Total Sales] )

Total Orders = DISTINCTCOUNT ( Orders[Order ID] )

Total Customers = DISTINCTCOUNT ( Orders[Customer ID] )

Avg Order Value = DIVIDE ( [Total Sales], [Total Orders] )
```
> Discount is a **rate (0–1)**, so use `AVERAGE`, not `SUM`. Format `Avg Discount %` and `Profit Margin %` as percentage.

## Shipping
```DAX
Avg Shipping Days =
AVERAGEX ( Orders, DATEDIFF ( Orders[Order Date], Orders[Ship Date], DAY ) )
```

## Loss Analysis
```DAX
Loss-making Sales = CALCULATE ( [Total Sales], Orders[Profit] < 0 )

Loss-making Lines = CALCULATE ( COUNTROWS ( Orders ), Orders[Profit] < 0 )
```

## Time Intelligence (needs a Date table)
Create a calculated table, then mark it as a date table and relate `'Calendar'[Date]` to `Orders[Order Date]` (many-to-one):
```DAX
Calendar =
ADDCOLUMNS (
    CALENDAR ( MIN ( Orders[Order Date] ), MAX ( Orders[Order Date] ) ),
    "Year", YEAR ( [Date] ),
    "Quarter", "Q" & QUARTER ( [Date] ),
    "Month No", MONTH ( [Date] ),
    "Month", FORMAT ( [Date], "MMM" )
)
```
Then (set `Month` to sort by `Month No`):
```DAX
Sales LY = CALCULATE ( [Total Sales], SAMEPERIODLASTYEAR ( 'Calendar'[Date] ) )

Sales YoY % = DIVIDE ( [Total Sales] - [Sales LY], [Sales LY] )

Profit LY = CALCULATE ( [Total Profit], SAMEPERIODLASTYEAR ( 'Calendar'[Date] ) )

Sales YTD = TOTALYTD ( [Total Sales], 'Calendar'[Date] )
```

## Expected values (check your measures against these)
| Measure | Value |
|---|---|
| Total Sales | 2,297,200.86 |
| Total Profit | 286,397.02 |
| Profit Margin % | 12.47% |
| Avg Discount % | 15.62% |
| Total Quantity | 37,873 |
| Total Orders | 5,009 |
| Total Customers | 793 |
| Avg Shipping Days | 3.96 |

## Ranking
```DAX
Sub-Category Rank =
RANKX ( ALL ( Orders[Sub-Category] ), [Total Sales], , DESC, DENSE )
```

## Conditional Formatting Helper
```DAX
Profit Colour = IF ( [Total Profit] < 0, "#C0392B", "#2E7D32" )
```
Use it under *Format > Conditional formatting > Font colour > Field value*.
