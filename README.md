# 🚲 Bike Buyers Sales Dashboard — Excel Data Analysis Project

An end-to-end data analysis project built entirely in Microsoft Excel, covering data cleaning, transformation, pivot table analysis, and an interactive dashboard — applied to a dataset of 1,000 potential bike buyers.

---

## 📌 Project Overview

This project explores what factors influence whether a customer purchases a bike. Using a raw dataset of 1,000 individuals with demographic and lifestyle attributes, I performed a full analysis pipeline — from messy raw data to a polished, filterable dashboard.

**Key question answered:** *What customer profiles are most likely to purchase a bike?*

---

## 📁 File Structure

```
📦 bike-buyers-dashboard/
 ┣ 📊 Excel_Project_Dataset.xlsx
 ┃  ┣ 🗂 bike_buyers        → Original raw dataset
 ┃  ┣ 🗂 working sheet      → Cleaned & transformed data
 ┃  ┣ 🗂 Pivot Table        → All pivot tables used for analysis
 ┗  ┗ 🗂 Dashboard          → Final interactive dashboard with slicers
```

---

## 🧹 Step 1 — Data Cleaning

The raw `bike_buyers` sheet contained several quality issues that were resolved in the `working sheet`:

### Duplicate Removal
- Used **Remove Duplicates** (Data tab) to eliminate any repeated rows based on the unique `ID` column.

### Column Header Standardisation
- Renamed malformed headers (e.g. `Marriedarital SingletatuSingle` → `Marital Status`) for clarity and consistency.

### Value Standardisation
- **Marital Status** — abbreviated values (`M`, `S`) expanded to `Married` / `Single` for readability.
- **Gender** — abbreviated values (`M`, `F`) expanded to `Male` / `Female`.

### Data Type Correction
- **Income** — confirmed as numeric (whole number), no currency symbol in raw data; formatted as `$#,##0` in the working sheet.
- **Age** — confirmed as integer; used as the base for the calculated field below.

---

## 🔧 Step 2 — Data Transformation

### Calculated Field: Age Brackets

A new column `Age Brackets` was added using a nested `IF` formula to segment customers into three age groups:

```excel
=IF(L2>54,"Old",IF(L2>=31,"Middle Aged","Adoloscent"))
```

| Age Range | Label |
|-----------|-------|
| ≤ 30 | Adoloscent |
| 31 – 54 | Middle Aged |
| 55+ | Old |

This field was used as a slicer and axis dimension in the dashboard.

---

## 📊 Step 3 — Pivot Table Analysis

Four pivot tables were created in the `Pivot Table` sheet to answer specific analytical questions:

| Pivot Table | Rows | Values | Insight |
|-------------|------|--------|---------|
| **Avg Income vs Purchase** | Gender | Average of Income | Male buyers earn more on average than non-buyers |
| **Commute Distance vs Purchase** | Commute Distance | Count of ID | Shortest commutes (0–1 mi) have the highest purchase volume |
| **Age Bracket vs Purchase** | Age Brackets | Count of ID | Middle Aged customers dominate purchases |
| **Occupation vs Purchase** | Occupation | Count of ID | Professionals are the top-buying occupation group |

---

## 📈 Step 4 — Charts & Visuals

The following charts were built from the pivot tables and embedded into the dashboard:

- **Clustered Bar — Average Income by Gender & Purchase Status**  
  Shows that buyers consistently earn more than non-buyers across both genders.

- **Line Chart — Bike Purchase by Commute Distance**  
  Purchases peak at 0–1 miles and decline sharply beyond 5 miles.

- **Clustered Bar — Purchase Count by Age Bracket**  
  Middle Aged customers account for the majority of both purchases and non-purchases.

- **Clustered Bar — Purchase Count by Occupation**  
  Professionals lead in bike purchases; Manual workers have the lowest count.

---

## 🎛️ Step 5 — Interactive Dashboard

The `Dashboard` sheet consolidates all visuals with **Excel Slicers** for dynamic filtering:

### Slicers Available
- **Marital Status** — Married / Single
- **Region** — Europe / North America / Pacific
- **Education** — Bachelors, Graduate Degree, High School, Partial College, Partial High School

All four charts respond simultaneously to slicer selections, enabling cross-dimensional exploration of the data.

---

## 💡 Key Findings

- **Income matters** — Bike buyers have a higher average income than non-buyers across both genders. Male buyers average ~$60,124 vs ~$56,208 for non-buyers.
- **Short commutes drive purchases** — Customers commuting 0–1 miles are the most likely to buy, suggesting recreational or last-mile use.
- **Age sweet spot** — Middle Aged customers (31–54) are by far the most active buyers (383 purchases vs 318 non-purchases).
- **Pacific region converts best** — Despite being the smallest region (192 customers), Pacific has the highest conversion rate at ~59%.
- **Professionals lead occupation-wise** — 150 out of 276 professionals purchased a bike (54% conversion rate).

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| Microsoft Excel | Data cleaning, transformation, pivot tables, charts, dashboard |
| Excel Slicers | Interactive filtering on the dashboard |
| Nested IF formulas | Age bracket calculated field |
| Remove Duplicates | Data quality step |

---

## 📷 Dashboard Preview

> *Open `Excel_Project_Dataset.xlsx` and navigate to the **Dashboard** sheet to interact with the live slicers and charts.*

---

## 🚀 How to Use

1. **Clone or download** this repository
2. Open `Excel_Project_Dataset.xlsx` in Microsoft Excel (2016 or later recommended for full slicer support)
3. Navigate to the **Dashboard** tab
4. Use the slicers on the left to filter by Marital Status, Region, or Education
5. All charts update automatically

---

## 👤 Author

**[Anurag Sharma]**  
Data Analyst Portfolio Project  
[LinkedIn](#https://www.linkedin.com/in/anurag-sharma-ba809233b/) ·

---

## 📄 License

This project is licensed under the [MIT License](LICENSE) — feel free to use, fork, and build on it.
