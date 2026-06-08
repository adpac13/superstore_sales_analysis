# superstore_sales_analysis
End-to-end data analytics project  Python, SQL, Matplotlib
Superstore Sales Analysis | End to End Data Analytics Project

A complete data analytics project that transforms raw retail data into actionable business insights through a full ETL pipeline and SQL data modeling. Superstore Sales Analysis | End-to-End Data Analytics Project

## Business Objective

Analyze 9,800 retail transactions from a US-based superstore (2015–2018) to answer 4 key business questions:

- Which **product category** generates the most revenue?
- Which **region** has the highest sales performance?
- What **seasonal patterns** exist in sales over time?
- How does **category performance vary by region**?

---

## Process

### 1. Data Extraction
- Dataset: [Superstore Sales — Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- 9,800 rows · 18 columns · 4 years of transactions (2015–2018)

### 2. Data Cleaning : Python & Pandas
- Converted `Order Date` and `Ship Date` from string to datetime format
- Fixed `Postal Code` from float to string, handled 11 null values
- Engineered 4 new columns: `Days to Ship`, `Order Month`, `Order Year`, `Quarter`

### 3. Data Modeling : SQL Star Schema
Built a star schema in SQLite with 1 fact table and 4 dimension tables:

### 4. Analysis — SQL Queries
- Revenue by category, region, and time period
- Cross-analysis of region vs category performance
- Seasonal trend analysis by year and quarter

### 5. Visualization — Python
- 4 analytical charts built with Matplotlib and Seaborn
- Each visualization answers a specific business question

### 6. Automation — Python & Task Scheduler
- Automated Excel report with 4 sheets and professional styling
- Runs daily at 7:00 AM via Windows Task Scheduler
- Filename includes timestamp: `reporte_ventas_YYYYMMDD.xlsx`

---

##  Key Findings

**1. Technology leads revenue despite fewer orders**
Technology generated $827K with only 1,813 orders vs Office Supplies which needed 5,909 orders to reach $705K — optimizing Technology conversion has a higher ROI than increasing Office Supplies volume.

**2. West & East concentrate 66% of total revenue**
West ($710K) and East ($669K) together account for two-thirds of total revenue. South generates only 15% of total revenue — a significant growth opportunity.

**3. Q4 is consistently the strongest quarter across all years**
Every year without exception, Q4 outperforms all other quarters — peaking at $278K in 2018 Q4, nearly double 2015 Q4 ($177K). Q1 is consistently the weakest quarter.

**4. Technology dominates in every region**
Technology is the #1 category in all 4 regions. The biggest gap is in East ($263K) where it nearly doubles Office Supplies ($199K). West is the most competitive region — Technology and Furniture are separated by only $2K.

**5. 50% revenue growth from 2015 to 2018**
Total revenue grew from $479K in 2015 to $722K in 2018, demonstrating consistent business health across all regions and categories.

---

##  Visualizations

### Revenue by Category
![Revenue by Category](visualizations/grafica_categorias.png)

### Revenue by Region
![Revenue by Region](visualizations/grafica_regiones.png)

### Sales Trend by Year and Quarter
![Sales Trend](visualizations/grafica_tendencia.png)

### Revenue by Region and Category
![Revenue by Region and Category](visualizations/grafica_region_categoria.png)

---

##  Automated Report

The project includes a fully automated Excel report that:
- Connects to SQLite and runs all 4 queries automatically
- Generates a styled Excel file with 4 sheets
- Saves with timestamp in filename
- Runs daily at 7:00 AM via Windows Task Scheduler

---

##  How to Run

1. Clone this repository
2. Install dependencies:
```bash
pip install pandas matplotlib seaborn openpyxl jupyter
```
3. Place `superstoresales.csv` in `data/raw/`
4. Open and run `notebooks/01_cleaning.ipynb` cell by cell
5. The SQLite database and clean CSV will be generated automatically
6. Run `reporte_automatizado.py` to generate the Excel report
