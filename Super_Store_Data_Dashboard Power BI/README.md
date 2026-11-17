# 🛒 Super Store Sales Dashboard – Power BI

An interactive **Power BI** dashboard that analyses 4 years (2016–2019) of Super Store orders in the United States. It shows total sales, profit and quantity, and breaks sales down by **region, state, customer segment, product sub-category and year**.

**Created by:** Uzma Ejaz
**Report file:** [`Super_Store_Data_Dashboard.pbix`](Super_Store_Data_Dashboard.pbix)
**Dataset:** [`data/Sample_Superstore.xlsx`](data/Sample_Superstore.xlsx) (9,994 order lines, 5,009 orders, 793 customers, 49 states)

---

## 📸 Dashboard Preview
![Super Store Dashboard](images/dashboard.jpg)

---

## 🎯 Project Objective
Give management a one-page view of store performance so they can see **what sells, where it sells and how profitable it is**, and decide where to focus.

## 🛠️ Tools Used
- **Power BI Desktop** – data model and interactive visuals
- **Power Query** – data loading
- **DAX** – measures (see [`docs/DAX_Measures.md`](docs/DAX_Measures.md))
- **Excel** – source data

## 🗃️ Data Model
A single table, **`Orders`**, loaded from the `Orders` sheet of the Excel file. See [`docs/Data_Dictionary.md`](docs/Data_Dictionary.md) for all columns.

## 📊 Dashboard Contents
**Page:** Data Analysis Report (10 visuals)

| Visual | Type | Shows |
|---|---|---|
| Sum of Sales, Discount, Profit, Quantity | KPI cards | Headline totals |
| Sum of Sales by Region | Donut chart | Share of sales per region |
| Sum of Sales by Segment | Pie chart | Consumer, Corporate, Home Office |
| State | Map | Where sales happen in the US |
| Sum of Sales by Sub-Category | Funnel chart | Best to worst sub-categories |
| Sum of Sales by Year | Ribbon chart | Sales trend 2016–2019 |

## 🔑 Key Metrics
| Metric | Value |
|---|---|
| Total Sales | **2.30M** (2,297,201) |
| Total Profit | **286.4K** (286,397) |
| Profit Margin | **12.5%** |
| Total Quantity | **37,873** |
| Average Discount | **15.6%** |
| Total Orders / Customers | 5,009 / 793 |

> The dashboard's "Sum of Discount" card shows 1.56K, which adds up discount rates and is not meaningful. The correct figure is the **average discount of 15.6%**.

## 💡 Key Insights
**From the dashboard**
- **Region:** **West** leads with 725.46K sales (31.58%), then **East** 678.78K (29.55%), **Central** 501.24K (21.82%) and **South** 391.72K (17.05%). West and East together bring about 61% of sales.
- **Segment:** **Consumer** is the largest with 1.16M (50.56%), then **Corporate** 0.71M (30.74%) and **Home Office** 0.43M (18.7%).
- **Sub-category:** **Phones** (330K) and **Chairs** (328K) are the top sellers, followed by Storage (224K) and Tables (207K). **Fasteners** (3.0K), **Labels** (12.5K) and **Envelopes** (16.5K) sell the least.
- **Trend:** Sales dipped slightly from 484K (2016) to 471K (2017), then grew strongly to 609K (2018) and **733K (2019)**, a 56% rise from 2017 to 2019.

**Additional analysis from the dataset**
- **Category:** Technology has the highest sales (836K) and best margin (17.4%). **Furniture** sells 742K but earns only a **2.5% margin** (profit 18K), while Office Supplies earns 17.0%.
- **Loss-making sub-categories:** **Tables** (-17.7K profit), **Bookcases** (-3.5K) and **Supplies** (-1.2K), even though Tables is a top-5 seller by sales.
- **Discounts hurt profit:** Orders with no discount earn a **29.5%** margin, 0–20% discount earns 11.9%, 20–40% loses 15.3%, and discounts above 40% lose **77.4%**.
- **States:** California (458K) and New York (311K) lead in sales. **Texas** (-25.7K), **Ohio** (-17.0K) and **Pennsylvania** (-15.6K) are the biggest loss-making states.
- **Shipping:** Average shipping time is 4.0 days; Standard Class is used for 60% of order lines.
- **Returns:** 296 orders (5.9% of all orders) were returned.

## 🚀 Business Recommendations
- Reduce or cap discounts above 20%, since they turn profitable sales into losses.
- Review pricing and discounts for **Tables, Bookcases and Supplies**, and for Texas, Ohio and Pennsylvania.
- Focus marketing on **Technology** (Phones, Copiers, Accessories), which combines high sales and high margin.
- Keep investing in the **West and East** regions, and look for growth opportunities in the South.
- 
## 📊 Dashboard Preview

### Superstore Sales & Profit Overview (2016–2019)
<img width="1222" height="745" alt="dashboard" src="https://github.com/user-attachments/assets/0e297c78-9be2-4bb1-9958-5629ea506913" />

## ▶️ How to Open
1. Install the free **Power BI Desktop**.
2. Open `Super_Store_Data_Dashboard.pbix`.
3. If Power BI asks for the data source, go to *Home > Transform data > Data source settings* and point it to `data/Sample_Superstore.xlsx`.
4. To see the map, enable *File > Options > Global > Security > Use Map and Filled Map visuals*.

## 📁 Repository Structure
```
Super-Store-Dashboard/
├── Super_Store_Data_Dashboard.pbix
├── README.md
├── data/
│   └── Sample_Superstore.xlsx
├── images/
│   └── dashboard.jpg
└── docs/
    ├── DAX_Measures.md
    ├── Data_Dictionary.md
    └── Dashboard_Improvement_Checklist.md
```

## 🔮 Future Improvements
- Add slicers (Year, Region, Category, Segment)
- Add pages for Products, Regions/States, and Customers/Shipping (see the checklist in `docs/`)
- Use average discount and profit margin % measures

## 🙏 Thank You
If you like this project, please ⭐ the repository!
