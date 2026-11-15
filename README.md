# Superstore Sales Analysis | Python & Data Analytics

## Project Overview

This project explores retail sales data to identify business performance trends, understand customer purchasing behaviour, evaluate product profitability and investigate the relationship between discounts and profit.

Using Python and data analysis techniques, I cleaned and transformed the dataset, performed exploratory data analysis (EDA), calculated key business metrics and developed visualisations to communicate actionable business insights.

The objective is to demonstrate how data analytics can support business decision-making and improve retail performance.

## Business Questions

This analysis focuses on the following questions:

1. How is the business performing in terms of revenue and profitability?
2. Which product categories and subcategories generate the highest profits?
3. Which regions contribute most to sales and profit?
4. Which customer segments contribute most to business performance?
5. Are high-spending customers necessarily the most profitable?
6. How do discounts relate to profit margins and loss-making transactions?
7. What monthly sales and profit trends can be identified?

## Tools & Technologies

- **Python** – Data analysis and manipulation
- **Jupyter Notebook** – Analysis environment
- **Pandas** – Data cleaning and analysis
- **NumPy** – Numerical operations
- **Matplotlib** – Data visualisation
- **Exploratory Data Analysis (EDA)** – Identifying patterns and trends

## Dataset & Data Cleaning

The project uses a Sample Superstore retail sales dataset.

- Original records: 10,800
- Records removed due to missing Order Date: 806
- Final cleaned records: 9,994
- Exact duplicate records in the cleaned dataset: 0
- Missing postal codes retained where other essential information was available: 11

Data preparation included:
- Standardising column names.
- Identifying and handling missing values.
- Checking duplicate records.
- Converting date fields into appropriate formats.
- Creating additional analytical columns, including year, month, profit margin and discount level.

## Key Business Performance Metrics

The cleaned dataset produced the following overall results:

| Metric | Result |
|---|---:|
| Total Revenue | $2,297,200.86 |
| Total Profit | $286,397.02 |
| Profit Margin | 12.47% |
| Total Orders | 5,009 |
| Total Customers | 793 |
| Units Sold | 37,873 |
| Average Order Value | $458.61 |
| Loss-Making Line Items | 1,871 |

## Key Findings & Business Insights

### 1. Product Category Performance

- Technology generated the highest profit at $145,454.95.
- Office Supplies generated $122,490.80 in profit.
- Furniture generated only $18,451.27 in profit despite contributing 32.3% of total revenue.
- Furniture had the lowest profit margin at 2.49%.

**Business insight:** Furniture requires further investigation into pricing, discounting and product costs to improve profitability.

### 2. Subcategory Profitability

- **Copiers** generated the highest profit at **$55,617.82**, followed by **Phones** ($44,515.73) and **Accessories** ($41,936.64).
- **Tables** (-$17,725.48), **Bookcases** (-$3,472.56), and **Supplies** (-$1,189.10) were the only loss-making subcategories.
- High average discounts on **Tables** (26%) and **Bookcases** (21%) directly eroded margins across the Furniture category.

**Business insight:** Re-evaluating discount caps and supplier costs on Tables and Bookcases is essential to stop margin leakage in Furniture.

### 3. Regional Performance

- **West** led both revenue ($725,457.82) and profit ($108,418.45), achieving the highest regional profit margin at **14.94%**.
- **East** ranked second in revenue ($678,781.24) and profit ($91,522.78) with a **13.48%** profit margin.
- **Central** generated higher revenue ($501,239.89) than the **South** ($391,721.91), yet produced lower total profit ($39,706.36 vs. $46,749.43) and the lowest margin (**7.92%**).

**Business insight:** Central's heavy average discounting (24%, more than double the West's 11%) is compressing profitability. Tightening promotional controls in the Central region offers immediate margin upside.

### 4. Customer Segments & High-Spending Customers

- **Consumer** is the largest segment by revenue and profit, followed by **Corporate** and **Home Office**.
- High-spending customers are **not automatically the most profitable**—several top-revenue accounts resulted in net losses due to heavily discounted bulk orders in low-margin subcategories (such as Tables and Machines).

**Business insight:** Account management and loyalty incentives should be tiered by **customer profit contribution** rather than gross order value alone.

### 5. Discount Sensitivity

- Transactions with **0% discount** consistently delivered healthy positive margins.
- Profit margins decline sharply once discounts exceed **20%**, with discount tiers above **30%–40%** almost universally resulting in net financial losses.
- Overall, **1,871 line items (18.72%)** were sold at a loss.

**Business insight:** Implementing automated approval thresholds for discounts above 20% can prevent unprofitable order fulfillment.

### 6. Monthly Sales & Seasonality Trends

- Sales and profit follow a strong **Q4 seasonal surge**, peaking consistently in **November and December** alongside a secondary spike in **September**.
- **January and February** represent the slowest months of the year for both order volume and revenue.

**Business insight:** Inventory procurement and marketing spend should scale ahead of Q4 peak demand, while Q1 promotions should focus on high-margin Office Supplies and Technology items rather than deep-discount Furniture clearance.

---

## Visualisations

All generated charts are available in the [`screenshots/`](./screenshots) directory:

| Chart | Description |
|---|---|
| `01_category_revenue.png` | Total revenue comparison across Product Categories |
| `02_category_profit.png` | Total profit comparison across Product Categories |
| `03_subcategory_profitability.png` | Profit, sales, and average discount breakdown by Subcategory |
| `04_regional_revenue.png` | Total revenue across geographic Regions |
| `05_regional_profit.png` | Total profit across geographic Regions |
| `06_discount_profitability.png` | Impact of discount tiers on average profit and margin |
| `07_monthly_revenue.png` | Historical monthly revenue trend |
| `08_monthly_profit.png` | Historical monthly profit trend |
| `09_monthly_average_sales.png` | Average sales seasonality by calendar month |
| `10_monthly_average_profit.png` | Average profit seasonality by calendar month |

---

## Strategic Recommendations

1. **Cap Discounts at 20%:** Establish guardrails requiring manager approval for discounts above 20%, particularly on Furniture items.
2. **Restructure Furniture Pricing:** Audit vendor costs and shipping expenses for **Tables** and **Bookcases**, or bundle them with higher-margin accessories.
3. **Audit Central Region Promotions:** Align Central region discounting practices closer to the West and East regions to recover lost margin.
4. **Shift to Profit-Based Customer Retention:** Focus retention campaigns on high-margin repeat buyers rather than high-revenue, low-margin discount seekers.

---

## Repository Structure

```text
Superstore-Sales-Analysis/
├── data/
│   └── superstore_sales.csv          # Raw Superstore retail dataset
├── outputs/
│   ├── category_analysis.csv         # Aggregated metrics by category
│   ├── subcategory_analysis.csv      # Aggregated metrics by subcategory
│   ├── region_analysis.csv           # Aggregated metrics by region
│   ├── segment_analysis.csv          # Aggregated metrics by customer segment
│   ├── customer_analysis.csv         # Customer-level revenue & profit summary
│   ├── top_10_customers.csv          # Top 10 customers by revenue
│   ├── top_profitable_customers.csv  # Top 10 most profitable customers
│   ├── least_profitable_customers.csv# Bottom 10 loss-making customers
│   ├── discount_analysis.csv         # Metrics by exact discount rate
│   ├── discount_band_analysis.csv    # Metrics by discount tier
│   ├── monthly_analysis.csv          # Year-Month time-series metrics
│   ├── seasonality_analysis.csv      # Calendar month averages
│   └── executive_summary.csv         # High-level business KPIs
├── screenshots/                      # Exported visualisations (01–10)
├── Superstore_Sales_EDA.ipynb        # Main Jupyter Notebook with code & commentary
└── README.md                         # Project documentation and findings