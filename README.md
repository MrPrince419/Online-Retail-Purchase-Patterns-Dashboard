## 📊 Online Retail Purchase Patterns Dashboard Documentation

**Online Retail Purchase Patterns Dashboard**  
*Developed by: [Prince Uwagboe]*

---

## 1️⃣ Introduction

**Overview**  
The Online Retail Purchase Patterns Dashboard provides a comprehensive, interactive view of sales performance for a two-year period (2010–2011). It enables business users to track total revenue, customer engagement, product performance, and sales trends over time.

**Purpose & Objectives**
- Visualize total revenue, customer count, and invoice volume.
- Identify top-selling products and customer segments.
- Monitor geographic sales distribution.
- Analyze seasonal/monthly sales trends.
- Enable stakeholders to make data-driven decisions.

**Business Problem Addressed**  
Retail businesses often lack accessible, real-time insights into sales drivers and customer behavior. This dashboard consolidates data into a single, intuitive interface.

---

## 2️⃣ Data Sources

**Primary Source**
- **Excel File**  
  - Source: Online Retail sales data (2010–2011) Kaggle  
  - Access: Manual upload

**Data Extraction**
- Imported via Excel workbook into Power BI Desktop.

---

## 3️⃣ Data Cleaning and Preparation

**Tools Used**
- Microsoft Excel
- Power BI Power Query Editor

**Steps**
- Removed duplicates (~5,231 rows).
- Removed rows with null Customer IDs or invalid dates.
- Filtered out negative quantities.
- Converted data types (dates, numeric fields).
- Split InvoiceDate into Year, Month, Day.

**Challenges**
- Multiple header rows and mixed data types.
- Cleaned manually in Excel and validated in Power Query.

---

## 4️⃣ Data Modeling

**Model**
- Flat/Single Table Model for simplicity and performance.

**Relationships**
- Single fact table: `Year 2010–2011`

**Calculated Columns**
- `YearOnly` (from InvoiceDate)

**DAX Measures**
- `% of Total Sales`
- `Product Sales Rank`
- `Average Order Value`
- `Avg Quantity per Order`

**Hierarchies**
- Year > Quarter > Month > Day

---

## 5️⃣ Data Transformation

**Power Query Steps**
- Removed empty and duplicate rows.
- Filtered invalid quantities.
- Ensured correct data types.
- Created date hierarchy columns.

**Reasoning**
- To maintain data integrity and optimize visual performance.

---

## 6️⃣ Dashboard Design and Visualization

**Layout Principles**
- **KPI Summary Row**  
  - TotalPrice, Customer ID Count, Invoice Count  
    ![Total Price](assets/sum%20of%20totalprice.png)  
    ![Customer Count](assets/count%20of%20customer%20id.png)  
    ![Invoice Count](assets/count%20of%20invoice.png)

- **Top Sales by Description**  
  - Bar chart with conditional formatting  
    ![Top Products](assets/sum%20of%20totalprice%20by%20description.png)

- **Geographic Sales**  
  - Filled map visualization  
    ![Country Map](assets/sum%20of%20totalprice%20by%20country.png)

- **Order Value & Quantity Cards**  
    ![Average Order Value](assets/average%20order%20value.png)  
    ![Avg Quantity per Order](assets/avg%20quantity%20per%20order.png)

- **Sales by Month**  
  - Area chart  
    ![Monthly Sales](assets/sum%20of%20totalprice%20by%20month.png)

- **Sales by Customer**  
  - Line chart  
    ![Customer Sales](assets/sum%20of%20totalprice%20by%20customer%20id.png)

- **Slicer Panel**  
  - Year and Month  
    ![Year/Month Slicer](assets/year,%20month.png)

**Design**
- Dark theme for high contrast.
- Consistent color palette.
- Minimal clutter.
- Tooltips showing % of Total Sales and Rank.

**Interactivity**
- Cross-filtering between visuals.
- Drill-down via slicers.
- Tooltips with key KPIs.

---

## 7️⃣ DAX Calculations

| Measure                    | Formula                                                                                      | Purpose                                      |
|----------------------------|----------------------------------------------------------------------------------------------|----------------------------------------------|
| **% of Total Sales**       | `DIVIDE(SUM([TotalPrice]), CALCULATE(SUM([TotalPrice]), ALL('Year 2010-2011')))`            | Product’s share of total revenue.            |
| **Product Sales Rank**     | `RANKX(ALL('Year 2010-2011'[Description]), CALCULATE(SUM([TotalPrice])), , DESC)`           | Rank products by revenue.                    |
| **Average Order Value**    | `DIVIDE(SUM([TotalPrice]), DISTINCTCOUNT([Invoice]))`                                       | Tracks avg. value per order.                 |
| **Avg Quantity per Order** | `DIVIDE(SUM([Quantity]), DISTINCTCOUNT([Invoice]))`                                         | Tracks avg. items per order.                 |
| **YearOnly**               | `YEAR([InvoiceDate])`                                                                       | Extracted year for filtering.                |

---

## 8️⃣ Performance Optimization

- Removed unnecessary columns.
- Limited calculated columns.
- Applied conditional formatting efficiently.
- Tested slicers and cross-filtering for speed.

---

## 9️⃣ Testing and Validation

**Data Validation**
- Cross-checked Power BI KPIs against Excel source.
- Verified totals and customer counts.
- Validated slicer behavior.

**User Testing**
- Manually tested slicer combinations and interactivity.

---

## 🔟 Challenges and Solutions

| Challenge                    | Solution                                              |
|------------------------------|-------------------------------------------------------|
| Duplicate & dirty data       | Cleaned in Excel and Power Query.                      |
| Data model complexity        | Simplified to single table.                           |
| Missing dimension values     | Excluded or filled.                                  |
| Performance optimization     | Optimized queries and visuals.                       |

*Reddit threads (r/PowerBI, r/dataanalysis) guided some design and optimization decisions.*

---

## 1️⃣1️⃣ Conclusion

The Online Retail Purchase Patterns Dashboard showcases a powerful, easy-to-use tool for analyzing sales trends, customer behavior, and product performance. It demonstrates a full range of Power BI skills including data preparation, modeling, DAX, design, and interactivity.

---

## 📁 Visual Gallery

All chart images used are located in the `assets/` folder:

### Average Order Value
![Average Order Value](assets/average%20order%20value.png)

### Average Quantity per Order
![Avg Quantity per Order](assets/avg%20quantity%20per%20order.png)

### Year and Month Slicer
![Year/Month Slicer](assets/year,%20month.png)

### Top Products by Total Price
![Top Products](assets/sum%20of%20totalprice%20by%20description.png)

### Monthly Sales
![Monthly Sales](assets/sum%20of%20totalprice%20by%20month.png)

### Customer Sales
![Customer Sales](assets/sum%20of%20totalprice%20by%20customer%20id.png)

### Invoice Count
![Invoice Count](assets/count%20of%20invoice.png)

### Total Price
![Total Price](assets/sum%20of%20totalprice.png)

### Customer Count
![Customer Count](assets/count%20of%20customer%20id.png)

### Geographic Sales by Country
![Country Map](assets/sum%20of%20totalprice%20by%20country.png)

---