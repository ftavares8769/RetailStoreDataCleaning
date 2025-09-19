# 🛒 Retail Sales Data Cleaning & Visualization Project

## 📌 Project Overview
This project showcases the **end-to-end process of cleaning messy transactional retail data and building a professional Power BI dashboard**.  
The focus is on **data quality, imputation decisions, and producing business-ready visuals** that allow for actionable insights.

---

## 📂 Project Structure
- **DataCleaning.ipynb / DataCleaning.html** → Jupyter Notebook with the full cleaning process and explanations.  
- **cleaned_data.csv** → Final cleaned dataset ready for analysis and visualization.  
- **DataVis.pbix** → Power BI dashboard file.  
- **DataVis.pdf** → Static PDF export of the dashboard for quick review.

---

## 🧹 Data Cleaning Steps

### 🔍 Thought Process
With no data dictionary provided, I began by exploring the dataset using:
- `head()` → understand column contents and structure.  
- `info()` → check dtypes and column consistency.  
- `isna().sum()` → identify missing values and their scope.  

From there, I created three categories:  
- **Must-fix** (errors that affect integrity).  
- **Optional** (changes useful for modeling, not needed here).  
- **Investigate further** (columns needing deeper inspection).  

For example, I corrected `Quantity` and `Transaction Date` dtypes. I considered one-hot encoding `Location`, but preserved text labels since they were more valuable for **Power BI visuals**.

---

### 🛠 Handling Missing Values
1. **Item** → Imputed with `"Unknown_Item"` since product identity is key, and many rows still contained valid prices.  
2. **Price Per Unit** → Imputed using the dataset’s **empirical distribution**.  
   - Before applying, I considered **bias testing** (checking if the sample distribution was skewed relative to the full data).  
   - This ensured imputations were **statistically sound** and avoided artificially inflating/deflating certain categories.  
3. **Quantity** → Replaced logically (e.g., 0 where valid), then cast to integers.  
4. **Total Spent** → Recalculated as `Price Per Unit × Quantity` when missing.  

This structured approach balanced **statistical rigor** with **business interpretability**, making the dataset suitable for both modeling and visualization.

---

### 💡 Discount Column Insights
During exploration, I expected discounted transactions to lower **average spend**. Surprisingly, averages for discounted vs non-discounted orders were nearly identical.  

I hypothesized that customers might purchase **larger quantities** when receiving a discount, offsetting the lower unit price. However, the data showed only a marginal difference in quantities (5.53 vs 5.51).  

This revealed that discounts did **not materially influence purchasing behavior** in this dataset, a useful insight for both business interpretation and feature evaluation.

---

## 📊 Power BI Dashboard
The interactive dashboard (see `DataVis.pbix`) highlights **retail sales performance** across multiple perspectives.

### Key Metrics (KPIs)
- **Total Revenue**: `$1.60M`  
- **Average Order Value**: `$129.6`  
- **% Transactions with Discount**: `34.93%`

### Main Visuals
- **Revenue & Orders by Year/Quarter** → Tracks growth trends over time.  
- **Revenue by Category** → Identifies top-performing product categories.  
- **Item Quantity by Discount Applied** → Compares purchasing behavior with/without discounts.  
- **Breakdown by Location & Payment Method** → Highlights customer preferences.

---

## 🚀 Tools & Technologies
- **Python / Pandas** → Data cleaning & preparation.  
- **Power BI** → Data visualization & dashboard building.  
- **CSV / Jupyter Notebooks** → Documentation & reproducibility.  

---

## ✅ Key Takeaways
- Strong emphasis on **data quality** through careful imputation choices.  
- Demonstrates **analytical workflow**: from raw data → cleaned dataset → insights in a dashboard.  
- Consideration of **statistical bias** in imputations shows understanding beyond simple fixes.  
- Produces a **business-ready deliverable** demonstrating both technical and communication skills.

---

## 📎 How to Use
1. Open `DataCleaning.ipynb` (or `.html`) to review the cleaning process.  
2. Explore the cleaned dataset via `cleaned_data.csv`.  
3. Open `DataVis.pbix` in Power BI Desktop to interact with the dashboard.  
4. Review `DataVis.pdf` for a static version.

---

## 👤 Author
**Francisco Tavares**  
Business Management & Data Analytics | Portfolio Project
