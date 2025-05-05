## 📊 Online Retail Purchase Patterns Dashboard

*By [Prince Uwagboe](https://github.com/MrPrince419)*

![Dashboard Overview](assets/dashboard%20overview.png)

---

## Table of Contents

1. [Introduction](#introduction)  
2. [Key Features](#key-features)  
3. [Technologies Used](#technologies-used)  
4. [Data Sources](#data-sources)  
5. [Data Cleaning and Preparation](#data-cleaning-and-preparation)  
6. [Data Modeling](#data-modeling)  
7. [Data Transformation](#data-transformation)  
8. [Dashboard Design and Visualization](#dashboard-design-and-visualization)  
9. [DAX Calculations](#dax-calculations)  
10. [How to Use](#how-to-use)  
11. [Results and Insights](#results-and-insights)  
12. [Skills Demonstrated](#skills-demonstrated)  
13. [Visual Gallery](#visual-gallery)  
14. [Contact](#contact)

---

## 1️⃣ Introduction

The **Online Retail Purchase Patterns Dashboard** provides a detailed, interactive analysis of retail sales from 2010–2011. It empowers business users to explore revenue drivers, customer behavior, product trends, and geographic sales performance.

---

## 2️⃣ Key Features

- KPI cards summarizing total sales, customer count, and invoices.
- Top-selling product ranking with conditional formatting.
- Geographic sales mapping.
- Year and month slicers for dynamic filtering.
- Advanced DAX calculations including % of total sales and ranking.
- Interactive tooltips displaying key insights.
- Clean, professional dark theme with optimized layout.

---

## 3️⃣ Technologies Used

- **Tools**: Power BI, Microsoft Excel, Power Query  
- **Languages**: DAX (Data Analysis Expressions)  
- **Data Source**: Kaggle Online Retail dataset (2010–2011)

---

## 4️⃣ Data Sources

**Primary Source**  
- Excel workbook (uploaded manually to Power BI)

**Extraction Method**  
- Imported directly into Power BI Desktop.

**Access**  
- File included in this repository: `online retail purchase patterns dashboard.pbix`

---

## 5️⃣ Data Cleaning and Preparation

- Removed ~5,231 duplicate rows.
- Removed rows with null Customer IDs or invalid dates.
- Filtered out negative quantities and non-standard entries.
- Converted data types for accuracy (dates, numeric fields).
- Created year, month, and day columns for time analysis.

**Tools Used**: Excel, Power Query

---

## 6️⃣ Data Modeling

- **Model**: Flat, single-table model for performance and simplicity.
- **Relationships**: Single fact table (`Year 2010–2011`).
- **Calculated Columns**:  
  - `YearOnly` (extracted from InvoiceDate).
- **Hierarchies**: Year > Quarter > Month > Day.

---

## 7️⃣ Data Transformation

Performed in Power Query:
- Removed empty and duplicate rows.
- Filtered invalid quantities.
- Validated data types.
- Created date hierarchy columns for time-based filtering.

---

## 8️⃣ Dashboard Design and Visualization

**Layout Principles**  
- **KPI Summary Row**: Total Sales, Customers, Invoices.  
- **Main Charts**:
  - Bar chart for top products.
  - Area chart for monthly sales.
  - Map visual for geographic sales.
  - Line chart for customer sales trends.
- **Slicer Panel**: Year and month filters.
- **Interactivity**: Tooltips, cross-filtering, dynamic slicers.

**Design Best Practices**  
- Dark theme for high contrast.
- Minimal clutter and consistent color scheme.
- Tooltips to enhance user experience.

---

## 9️⃣ DAX Calculations

| Measure                    | Formula                                                                                      | Purpose                                      |
|----------------------------|----------------------------------------------------------------------------------------------|----------------------------------------------|
| **% of Total Sales**       | `DIVIDE(SUM([TotalPrice]), CALCULATE(SUM([TotalPrice]), ALL('Year 2010-2011')))`            | Product’s share of total revenue.            |
| **Product Sales Rank**     | `RANKX(ALL('Year 2010-2011'[Description]), CALCULATE(SUM([TotalPrice])), , DESC)`           | Rank products by revenue.                    |
| **Average Order Value**    | `DIVIDE(SUM([TotalPrice]), DISTINCTCOUNT([Invoice]))`                                       | Average value per order.                     |
| **Avg Quantity per Order** | `DIVIDE(SUM([Quantity]), DISTINCTCOUNT([Invoice]))`                                         | Average items per order.                     |
| **YearOnly**               | `YEAR([InvoiceDate])`                                                                       | Extracted year for filtering.                |

---

## 🔟 How to Use

1. Clone or download this repository.
2. Open `online retail purchase patterns dashboard.pbix` in Power BI Desktop.
3. Use slicers to filter data by year or month.
4. Hover over visuals to view detailed tooltips including % of total sales and product rank.

---

## 1️⃣1️⃣ Results and Insights

- **Top-selling product**: DOTCOM POSTAGE (0.02% of total revenue).  
- **Peak sales months**: November and December.  
- **Largest market**: Canada.  
- Sales trends showed significant seasonal increases in Q4.

---

## 1️⃣2️⃣ Skills Demonstrated

- Data cleaning and preparation (Excel, Power Query).
- Data modeling and DAX calculations.
- Advanced visual design and conditional formatting.
- Interactive dashboard development.
- Comprehensive project documentation.
- Problem-solving and troubleshooting.

---

## 1️⃣3️⃣ Visual Gallery

| Visual | Description | Image |
|--------|-------------|-------|
| **Dashboard Overview** | Overview of the entire dashboard. | ![Dashboard Overview](assets/dashboard%20overview.png) |
| **Total Price KPI** | Total revenue overview. | ![Total Price](assets/sum%20of%20totalprice.png) |
| **Customer Count KPI** | Total unique customers. | ![Customer Count](assets/count%20of%20customer%20id.png) |
| **Invoice Count KPI** | Total invoices/orders. | ![Invoice Count](assets/count%20of%20invoice.png) |
| **Average Order Value** | Average revenue per order. | ![Average Order Value](assets/average%20order%20value.png) |
| **Avg Quantity per Order** | Average items per order. | ![Avg Quantity](assets/avg%20quantity%20per%20order.png) |
| **Top Products** | Bar chart with conditional formatting. | ![Top Products](assets/sum%20of%20totalprice%20by%20description.png) |
| **Sales by Month** | Area chart showing monthly sales trend. | ![Monthly Sales](assets/sum%20of%20totalprice%20by%20month.png) |
| **Customer Sales** | Line chart of customer sales. | ![Customer Sales](assets/sum%20of%20totalprice%20by%20customer%20id.png) |
| **Sales by Country** | Map showing geographic sales distribution. | ![Country Map](assets/sum%20of%20totalprice%20by%20country.png) |
| **Year/Month Slicer** | Dynamic filtering by year and month. | ![Year/Month Slicer](assets/year,%20month.png) |

---

## 1️⃣4️⃣ Contact

**LinkedIn**: [Prince Uwagboe](https://www.linkedin.com/in/princeuwagboe)  
**Email**: princeuwagboe44@outlook.com

---
