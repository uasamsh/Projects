# Dashboard Review & Next Steps

Review of `Super_Store_Data_Dashboard.pbix` (1 page, 10 visuals, 1 table). All numbers on the page were verified against `data/Sample_Superstore.xlsx` and match.

## ✅ Verified correct
Sales 2.30M, Profit 286K, Quantity 38K, Region split, Segment split, Sales by Year and Sub-Category values all match the dataset.

## ⚠️ Fix in the existing page
| # | Issue | Fix |
|---|---|---|
| 1 | **Discount card shows SUM (1.56K).** Discount is a rate, so the real figure is the **average = 15.6%**. | Change to Average (or use measure `Avg Discount %`) and format as %. |
| 2 | **Profit card is cut off ("286…").** Real value is 286,397. | Widen the card or set display units to Thousands (286.4K). |
| 3 | **Map needs the Map visual setting.** On a PC where *File > Options > Global > Security > "Use Map and Filled Map visuals"* is off, the map shows an error box. | Enable that option before taking screenshots or sharing. |
| 4 | **Ribbon chart uses Order Date and Ship Date** to Day level. | Keep only Order Date at Year (or Quarter). |
| 5 | **Page name "reports Q & A"**. | Rename to "Sales Overview". |
| 6 | **No slicers.** | Add slicers for Year, Region, Category, Segment. |
| 7 | **Cards slightly overlap.** | Select the 4 cards > Format > Align and distribute. |
| 8 | **Profit and Category are not shown anywhere except one card.** | Add the pages below. |

## 🧩 Pages to add (build in Power BI Desktop)
Use the measures in `DAX_Measures.md`.

**Page 2 – Products**
- Clustered bar: `Sub-Category` × `Total Profit` (shows Tables, Bookcases, Supplies in loss)
- Column chart: `Category` × `Total Sales` and `Profit Margin %`
- Table: Top 10 `Product Name` by `Total Sales`
- Scatter: X = `Avg Discount %`, Y = `Profit Margin %`, Details = `Sub-Category`

**Page 3 – Regions & States**
- Filled map or bar chart: `State` × `Total Profit` (conditional colour with `Profit Colour`)
- Matrix: `Region` > `State` with Sales, Profit, Margin %

**Page 4 – Customers & Shipping**
- Bar: Top 10 `Customer Name` by `Total Sales`
- Donut: `Ship Mode` × `Total Orders`
- Card: `Avg Shipping Days`, `Total Customers`

Add a **Page navigator** (Insert > Buttons > Navigator > Page navigator) on every page.

## 📦 Project files
| File | Status |
|---|---|
| `Super_Store_Data_Dashboard.pbix` | ✅ Included |
| `data/Sample_Superstore.xlsx` | ✅ Included |
| `images/dashboard.jpg` | ✅ Included |
| `README.md` | ✅ Included |
| `docs/DAX_Measures.md`, `Data_Dictionary.md` | ✅ Included |
| Extra pages 2–4 in the .pbix | ❌ To build in Power BI Desktop (steps above) |
