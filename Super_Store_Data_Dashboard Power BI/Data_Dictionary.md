# Data Dictionary – `Sample_Superstore.xlsx`

| Sheet | Rows | Description |
|---|---|---|
| **Orders** | 9,994 | One row per order line (used by the dashboard, table `Orders`) |
| Returns | 800 | Returned orders (`Returned`, `Order ID`), 296 unique orders |
| People | 4 | Regional manager per Region |
| Sheet1, Sheet2 | 0 | Empty sheets (can be deleted) |

## Orders columns
| Column | Type | Meaning |
|---|---|---|
| `A`` (first column) | Integer | Row number. The header is mistyped; it should be `Row ID` |
| Order ID | Text | Order identifier (5,009 unique) |
| Order Date / Ship Date | Date | 3 Jan 2016 to 30 Dec 2019 (order dates) |
| Ship Mode | Text | Standard Class, Second Class, First Class, Same Day |
| Customer ID / Customer Name | Text | Customer (793 unique) |
| Segment | Text | Consumer, Corporate, Home Office |
| Country/Region, City, State, Postal Code | Text/Number | Location (United States only, 49 states). Postal Code is missing for 11 rows (Burlington, Vermont) |
| Region | Text | West, East, Central, South |
| Product ID, Category, Sub-Category, Product Name | Text | Product hierarchy: 3 categories, 17 sub-categories |
| Sales | Decimal | Sales amount |
| Quantity | Integer | Units sold |
| Discount | Decimal 0–1 | Discount rate (0.2 = 20%) |
| Profit | Decimal | Profit (negative = loss) |

## Data quality notes
- No duplicate rows.
- Only missing values: `Postal Code` (11 rows, all Burlington, Vermont).
- `Discount` is a rate, so it must be **averaged**, not summed.
