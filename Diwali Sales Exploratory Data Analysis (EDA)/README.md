# 🪔 Diwali Sales Exploratory Data Analysis (EDA)

An end-to-end exploratory data analysis of Diwali-season retail sales in India using **Python, Pandas, Matplotlib, and Seaborn**. The project cleans the raw sales data and uncovers who buys, where they live, what they buy and how much they spend.

**Author:** Uzma Ejaz (Master of Computer Science)
**Notebook:** [`Diwali_Sales_EDA.ipynb`](https://github.com/uasamsh/Diwali-Sale-EDA/blob/main/Diwali_Sales_EDA.ipynb)
**Dataset:** `Diwali Sales Data.csv`

---

## 📌 Project Objective
Understand customer behaviour during the Diwali sale so a business can decide **which customers, regions, and product categories to target** to increase sales.

## 📂 Dataset Overview
- **Size:** 11,251 rows × 15 columns (11,239 rows after cleaning)
- **Columns:** `User_ID`, `Cust_name`, `Product_ID`, `Gender`, `Age Group`, `Age`, `Marital_Status`, `State`, `Zone`, `Occupation`, `Product_Category`, `Orders`, `Amount` (+ two empty columns: `Status`, `unnamed1`)

| Statistic (after cleaning) | Age | Orders per customer | Amount |
|---|---|---|---|
| Mean | 35.4 | 2.49 | 9,453.6 |
| Median | 33 | 2 | 8,109 |
| Min / Max | 12 / 92 | 1 / 4 | 188 / 23,952 |

## 🛠️ Tools & Libraries
- Python 3 (Jupyter Notebook)
- NumPy, Pandas
- Matplotlib, Seaborn

## 🔄 Workflow
1. **Import** libraries and load the CSV (`encoding='unicode_escape'`).
2. **Inspect** the data: `head()`, `shape`, `info()`, `isnull().sum()`, `describe()`.
3. **Clean** the data:
   - Dropped the empty columns `Status` and `unnamed1` (100% null).
   - Dropped 12 rows with a missing `Amount`.
   - Converted `Amount` from `float` to `int`.
   - Renamed `Marital_Status` to `Married` for readability.
4. **Visualise (EDA)** with count plots, box plots, bar plots, and line plots across Age, Gender, Age Group, Marital Status, State, Zone, Occupation, and Product Category.
5. **Conclude** with business observations.

## 📊 Key Insights
- 👩 **Women are the main buyers.** They place roughly 7 out of 10 orders and outnumber men in every age group.
- 🎂 **Age group 26–35 is the biggest segment** (about 3,250 women and 1,270 men), followed by 36–45 and 18–25.
- 💍 **Unmarried customers make more purchases** (about 6,500 unmarried vs 4,700 married).
- 💼 **Top occupations:** IT Sector (1,583), Healthcare (1,408), Aviation (1,310), and Banking (1,137).
- 🛍️ **Best-selling categories (by total orders):** Clothing & Apparel (~6,600), Food (~6,100), Electronics & Gadgets (~5,200) and Footwear & Shoes (~2,650).
- 🔢 **Orders are evenly spread** across 1–4 orders per customer (about 2,800 customers each), and the spending amount (median ≈ 8,100) is similar across order counts.
- 🗺️ **Regions:** average orders per customer are similar across states (roughly 2.4–2.6), with Himachal Pradesh and Uttarakhand slightly higher and Rajasthan slightly lower.

## 💡 Business Recommendations
- Target **women aged 26–45** with campaigns for Clothing, Food, and Electronics.
- Build offers for **IT, Healthcare, Aviation and Banking professionals**, the largest occupation groups.
- Bundle top categories (Apparel + Footwear, Electronics + Gadgets) to raise order value.

## 🚀 How to Run
```bash
git clone https://github.com/uasamsh/Diwali-Sale-EDA.git
cd Diwali-Sale-EDA
pip install numpy pandas matplotlib seaborn jupyter
jupyter notebook Diwali_Sales_EDA.ipynb
```
Keep `Diwali Sales Data.csv` in the same folder as the notebook.

## 🔮 Future Improvements
- Add total **sales amount** analysis by State, Zone, and Product Category (not only order counts).
- Build an interactive dashboard (Power BI / Tableau / Plotly).
- Add a simple customer segmentation or sales prediction model.

## 🙏 Thank You
If you found this project useful, please ⭐ the repository!
