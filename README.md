import pandas as pd

# Load and clean data
df = pd.read_csv("sales_data.csv")
df = df.drop_duplicates()
df = df.dropna(subset=["product"])
df["quantity"] = pd.to_numeric(df["quantity"], errors="coerce").fillna(0)
df["price"] = pd.to_numeric(df["price"], errors="coerce")
df["revenue"] = df["quantity"] * df["price"]

# Metrics
total_revenue = df["revenue"].sum()
total_orders = len(df)
revenue_by_product = df.groupby("product")["revenue"].sum().sort_values(ascending=False)
quantity_by_product = df.groupby("product")["quantity"].sum().sort_values(ascending=False)
best_product_by_revenue = revenue_by_product.idxmax()
best_product_revenue = revenue_by_product.max()

# Build report text (Markdown)
lines = []

lines.append("# Sales Data Analysis Report\n")
lines.append("## Project overview\n")
lines.append("This report analyzes the sales dataset to compute total revenue, identify the best-selling product, and summarize key metrics.\n")

lines.append("## Key metrics\n")
lines.append(f"- Total revenue: {total_revenue}\n")
lines.append(f"- Total orders (after cleaning): {total_orders}\n")
lines.append(f"- Best-selling product by revenue: {best_product_by_revenue} (revenue = {best_product_revenue})\n")

lines.append("## Revenue by product\n")
for product, rev in revenue_by_product.items():
    lines.append(f"- Product {product}: revenue = {rev}\n")

lines.append("\n## Quantity sold by product\n")
for product, qty in quantity_by_product.items():
    lines.append(f"- Product {product}: quantity sold = {qty}\n")

lines.append("\n## Data cleaning steps\n")
lines.append("- Removed duplicate rows.\n")
lines.append("- Dropped rows with missing product values.\n")
lines.append("- Filled missing quantities with 0 and converted quantity/price to numeric.\n")

lines.append("\n## Insights\n")
lines.append(f"- Product {best_product_by_revenue} generates the highest revenue, so it may deserve priority in inventory and marketing.\n")
lines.append("- Products with lower revenue or quantity may need pricing, promotion, or placement review.\n")

# Save report
with open("analysis_report.md", "w", encoding="utf-8") as f:
    f.writelines(lines)

print('Report generated: analysis_report.md')
