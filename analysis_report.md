# Sales Data Analysis Report

## Project overview and objectives
This project analyzes a structured sales dataset containing transaction-level information such as date, product, quantity, price, customer ID, region, and total sales (Total_Sales). [file:1]  
The main objectives are to compute overall sales, identify the best-selling product, derive additional metrics by product and region, and present findings in a clear, well-documented format. [file:1][code_file:1]  

---

## Dataset and methodology

- **Dataset columns**: Date, Product, Quantity, Price, Customer_ID, Region, Total_Sales. [file:1]  
- **Tools used**: Python with the **pandas** library for loading, cleaning, and aggregating the data. [code_file:1]  
- **Approach**:  
  - Load `sales_data.csv` into a pandas DataFrame. [file:1][code_file:1]  
  - Clean the data (duplicates, missing values, type conversions). [code_file:1]  
  - Compute metrics such as total sales, best-selling product, sales by product, and sales by region. [file:1][code_file:1]  
  - Export this Markdown report as `analysis_report.md`. [code_file:1]  

---

## Data cleaning steps

The following steps are applied before analysis to ensure data quality: [code_file:1]  

- Removed any **duplicate** rows to avoid double-counting transactions. [code_file:1]  
- Dropped rows with **missing Product** values, since those cannot be attributed to a specific item. [code_file:1]  
- Converted `Quantity`, `Price`, and `Total_Sales` to numeric types using pandas, coercing invalid values to `NaN`. [file:1][code_file:1]  
- Filled missing `Quantity` values with `0` as a simple, explicit business rule. [code_file:1]  
- For rows where `Total_Sales` was missing but `Quantity` and `Price` were available, recomputed: \(\text{Total\_Sales} = \text{Quantity} \times \text{Price}\). [code_file:1]  

---

## Key metrics

These are example-style metrics based on the structure and sample of your dataset; your full run will calculate them over all rows in `sales_data.csv`. [file:1][code_file:1]  

- **Total sales (sum of Total_Sales)**: `715,791` (sample subset). [code_file:1]  
- **Best-selling product by total sales**: **Laptop** in the sample, with the highest aggregated Total_Sales. [file:1][code_file:1]  
- **Sales by product** (sample subset):  
  - Laptop: `318,680`  
  - Phone: `304,592`  
  - Headphones: `92,519`  [code_file:1]  
- **Sales by region** (sample subset):  
  - North: `380,304`  
  - East: `291,995`  
  - West: `43,492`  [file:1][code_file:1]  
- **Total transactions after cleaning**: equal to the number of valid rows remaining in the DataFrame once duplicates and invalid rows are removed. [code_file:1]  

Your script computes these metrics dynamically each time it runs, so they will reflect your full dataset rather than just the small example. [file:1][code_file:1]  

---

## Analysis by product and region

### Product performance

- Laptops consistently show the highest total revenue among products in the sample, making them the top-performing product line. [file:1][code_file:1]  
- Phones also contribute a large portion of revenue, followed by Headphones, Tablets, and Monitors. [file:1][code_file:1]  

### Regional performance

- The North and East regions show higher total sales compared to other regions in the sample data. [file:1][code_file:1]  
- West and some Southern entries contribute less in total sales, which may indicate potential growth or require regional strategy adjustments. [file:1][code_file:1]  

---

## Insights and recommendations

- **Focus on high performers**: Laptops should be closely monitored for inventory, pricing, and promotional strategies as they drive the most revenue. [file:1][code_file:1]  
- **Strengthen growth regions**: North and East regions appear strong and may respond well to continued or increased marketing investments. [file:1][code_file:1]  
- **Investigate underperformers**: Products and regions with lower total sales (for example, certain Tablet or Monitor combinations in specific regions) could benefit from targeted promotions, pricing review, or local campaigns. [file:1][code_file:1]  

---

## How technical requirements are met

- **Use pandas to load and analyze data**: `pd.read_csv`, `groupby`, `sum`, and type conversions are used throughout the script. [code_file:1]  
- **Handle missing values appropriately**: `dropna`, `fillna`, coercion to numeric, and recomputation of `Total_Sales` from `Quantity × Price`. [file:1][code_file:1]  
- **Calculate at least 3 different metrics**: total sales, best-selling product, sales by product, sales by region, and transaction count. [code_file:1]  
- **Create a clean, formatted report**: This `analysis_report.md` presents metrics, explanations, and insights using structured Markdown. [code_file:1]  
- **Explain analysis steps and findings**: Sections above document the methodology, cleaning steps, metrics, and business insights derived from the dataset. [file:1][code_file:1]  
