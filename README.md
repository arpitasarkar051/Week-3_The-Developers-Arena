
# 🧾 Sales Data Analysis

## 📘 Project Overview and Objectives
This project analyzes a real-world-style sales dataset using **pandas** in Python to understand overall sales performance, identify the best-selling product, and summarize key metrics such as total revenue, sales by product, and sales by region.  

The main goals of this project are:
- Load and explore the dataset using `pandas`.
- Handle missing and duplicate values appropriately.
- Calculate essential business metrics.
- Generate a well-formatted, markdown-based report.
- Provide clean, reusable, and well-documented code.

---

## ⚙️ Setup and Installation Instructions

### Prerequisites
- google colab
- `pandas` library

### Installation Steps
1. **Clone this repository:**
   ```
   git clone https://github.com/yourusername/sales-data-analysis.git
   cd sales-data-analysis
   ```
2. **Install required packages:**
   ```
   pip install pandas
   ```
3. **Ensure your files are structured like this:**
   ```
   .
   ├── sales_analysis.py
   ├── sales_data.csv
   └── analysis_report.md
   ```
4. **Run the analysis:**
   ```
   python sales_analysis.py
   ```

After successful execution, the generated `analysis_report.md` file will contain key insights from your dataset.

---

## 🧩 Code Structure Explanation

### `sales_analysis.py`
Main Python script performing the data analysis. It consists of the following key functions:

| Function | Description |
|---------|-------------|
| `load_data()` | Loads `sales_data.csv` into a pandas DataFrame using `pd.read_csv`. |
| `clean_data()` | Handles missing values and duplicates, converts numeric columns, and recomputes missing totals if needed. |
| `compute_metrics()` | Computes total sales, best-selling product, sales by product, sales by region, and transaction count. |
| `generate_report()` | Creates `analysis_report.md`, summarizing metrics and insights in Markdown format. |
| `main()` | Orchestrates the full workflow: load → clean → analyze → report. |

Inline comments in the code explain each step in simple terms for readability and learning.

---

## 📊 Metrics and Findings (Example from Your Data)

Using your `sales_data.csv`, the script computes core metrics such as:  

- **Total Sales** (sum of `Total_Sales`):  
  `715,791` for the example subset shown. [code_file:1]  
- **Best-Selling Product** (by total revenue):  
  `Laptop` is the best-selling product in terms of total sales. [code_file:1]  
- **Sales by Product** (example subset):  
  - Headphones: `92,519`  
  - Laptop: `318,680`  
  - Phone: `304,592`  [code_file:1]  
- **Sales by Region** (example subset):  
  - East: `291,995`  
  - North: `380,304`  
  - West: `43,492`  [code_file:1]  

Your full dataset will produce the same style of metrics, just with totals calculated over all rows in `sales_data.csv`. [file:1]  

---

## 🧹 Data Cleaning Summary

The analysis includes a dedicated cleaning step to ensure reliable results:

- Removed duplicate records from the dataset.
- Dropped rows missing **product** names (cannot attribute sales without a product).
- Converted `Quantity`, `Price`, and `Total_Sales` to numeric types using pandas.
- Filled missing `Quantity` values with `0`, based on a clear business rule.
- Recomputed `Total_Sales` where possible using:  
  \[
  \text{Total\_Sales} = \text{Quantity} \times \text{Price}
  \]
  for rows with missing totals but valid quantity and price.  

This ensures that calculations such as total sales and best product are based on clean, consistent data.  

---

## 🧠 Insights

From the analyzed data (example subset and structure): [file:1][code_file:1]  

- **Laptops** generate the highest revenue, making them a key product line to prioritize in inventory and marketing.  
- Regions like **North** and **East** show stronger sales totals compared to others, indicating high-value markets.  
- Lower-performing products or regions may represent opportunities for targeted promotions or pricing strategies.  

These insights can guide business decisions on stock, promotions, and regional focus.  

---

## 📺 Screenshots (To Include)

For documentation and submission, you should capture:

1. **Terminal output** after running:
   ```
   python sales_analysis.py
   ```
   showing a message like:
   ```
   Report generated: analysis_report.md
   ```
2. **Report preview**: A screenshot of `analysis_report.md` opened in a Markdown viewer or code editor showing key metrics and sections.
3. **Data preview**: A screenshot of a Jupyter notebook or Python console with:
   ```
   import pandas as pd
   df = pd.read_csv("sales_data.csv")
   df.head()
   ```
   displaying the first few rows of your dataset.

---

## 🧩 How Technical Requirements Are Met

- ✅ **Use pandas to load and analyze data**  
  - `pd.read_csv` to load `sales_data.csv`.  
  - `groupby`, `sum`, and other pandas operations for aggregations.

- ✅ **Handle missing values appropriately**  
  - `dropna` to remove rows missing `Product`.  
  - `fillna(0)` for missing `Quantity`.  
  - Numeric conversion with `errors="coerce"` for robust cleaning.

- ✅ **Calculate at least 3 different metrics**  
  - Total Sales (sum of `Total_Sales`).  
  - Best-Selling Product by revenue.  
  - Sales by Product.  
  - Sales by Region.  
  - Total number of cleaned transactions.

- ✅ **Create a clean, formatted report**  
  - `analysis_report.md` is generated with structured headings, bullet points, and clear explanations.

- ✅ **Add comments explaining each step**  
  - `sales_analysis.py` includes comments in each function, describing what the step does and why.

---

## 🏁 Conclusion

This project demonstrates end-to-end sales data analysis using pandas, from loading and cleaning data to computing metrics and generating a professional Markdown report. You can extend it further with date-based analysis (monthly/quarterly trends), customer segmentation, or more advanced visualizations.  

---
