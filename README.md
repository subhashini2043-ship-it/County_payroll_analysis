# Cook County Payroll & Compensation Analysis

## 📊 Project Overview

This project analyzes **Cook County payroll data from Fiscal Year 2016 Q1 through Fiscal Year 2018 Q2** to understand workforce trends, payroll costs, compensation structure, tenure-based pay patterns, and payroll data quality.

The project was designed as a **portfolio-level Data Analyst project**, combining **Python for data cleaning and preparation** with **Excel for exploratory data analysis (EDA), PivotTables, and business insights**.

The dataset contains **234,295 payroll records** covering employees, job roles, bureaus, compensation, hire dates, and fiscal periods.

---

## 🎯 Business Objective

The objective is to answer five key business questions:

1. **Headcount & Pay Trend**
   Is payroll spending changing because of changes in workforce size or changes in average employee pay?

2. **Cost Concentration by Bureau**
   Which bureaus account for the largest share of payroll costs relative to their workforce?

3. **Pay Structure by Role**
   Which job titles have the highest average compensation?

4. **Tenure vs. Pay**
   Does compensation increase with employee tenure, and does pay growth slow after a certain point?

5. **Payroll Record Integrity**
   How many payroll records contain zero or negative pay, and how should these records be treated in compensation analysis?

---

## 🛠️ Tools & Technologies

* **Python**

  * Pandas
  * Data cleaning
  * Data quality checks
  * Feature engineering
* **Microsoft Excel**

  * Power Query
  * PivotTables
  * Calculated fields
  * Exploratory Data Analysis
  * Charts
* **GitHub**

  * Project documentation
  * Version control
  * Portfolio presentation

---

## 🧹 Data Cleaning & Preparation

The dataset was prepared before performing the business analysis.

Key steps included:

* Removed duplicate records
* Checked missing values
* Cleaned and converted `Base Pay` into a numeric field
* Standardized date fields
* Created `Negative Pay Flag`
* Created `Zero Pay Flag`
* Created `Tenure Years`
* Created `Tenure Group`
* Validated payroll records containing zero and negative values

### Tenure Calculation

Employee tenure was calculated using:

**Original Hire Date → June 30, 2018**

Tenure was then categorized into:

* 0–2 Years
* 2–5 Years
* 5–10 Years
* 10–20 Years
* 20+ Years

---

## 📈 Exploratory Data Analysis

### 1. Headcount & Pay Trend

Analyzed:

* Unique employees by fiscal period
* Total payroll
* Average base pay
* Workforce changes over time

The analysis shows that employee headcount declined across the period while average pay remained broadly stable to slightly higher in earlier periods. However, **2018 contains only Q1–Q2**, so its total payroll should not be directly compared with full-year figures.

---

### 2. Cost Concentration by Bureau

Analyzed each bureau using:

* Total payroll
* Average base pay
* Employee headcount

The analysis identified **Bureau of Health and Sheriff** as the two largest payroll cost centers.

A data-quality consideration was also identified: the Bureau field contains both high-level bureau names and specific facility names. This means bureau-level cost concentration should be interpreted carefully until the hierarchy is normalized.

---

### 3. Pay Structure by Role

Analyzed average compensation by `Job Title`.

To avoid misleading results from very small groups, job titles were restricted to those with **at least 20 employees**.

The analysis shows that **physician and medical leadership roles** occupy the highest levels of average compensation, while larger operational roles have lower average pay.

---

### 4. Tenure vs. Pay

Average base pay was compared across tenure groups.

| Tenure Group | Avg Base Pay |
| ------------ | -----------: |
| 0–2 Years    |   $11,762.94 |
| 2–5 Years    |   $14,665.64 |
| 5–10 Years   |   $17,133.10 |
| 10–20 Years  |   $17,674.50 |
| 20+ Years    |   $18,192.63 |

The results show a clear relationship between tenure and compensation. However, **pay growth becomes much smaller after 10 years**, indicating a potential post-10-year pay plateau.

This could warrant further investigation into compensation structures, pay-grade ceilings, and retention.

---

### 5. Payroll Record Integrity

Payroll records were classified using zero-pay and negative-pay flags.

The analysis identified:

* Normal payroll records
* Zero-pay records representing unpaid periods
* Negative-pay records consistent with payroll corrections

Zero-pay records were **excluded from average compensation calculations** but retained for headcount-related analysis.

Negative-pay correction records were also excluded from compensation averages where they could distort role-level results.

---

## 💡 Key Business Insights

* Workforce size declined over the analysis period.
* Payroll costs are concentrated among a small number of major bureaus.
* Physician and medical leadership roles have substantially higher average compensation.
* Compensation increases with tenure but **growth slows significantly after 10 years**.
* Zero-pay records should not be treated as normal compensation observations.
* Negative payroll records appear consistent with corrections and should be handled carefully in compensation analysis.
* The Bureau field requires normalization before publishing highly granular cost-center comparisons.

---

## 📌 Recommendations

1. Normalize the **Bureau → Office** hierarchy before using bureau-level cost analysis for external reporting.
2. Clearly flag **2018 as a partial year** in payroll trend analysis.
3. Investigate the workforce decline to determine whether it is driven by attrition, hiring restrictions, or bureau-specific changes.
4. Investigate the **post-10-year compensation plateau** as a potential retention concern.
5. Exclude zero-pay records from average compensation metrics while retaining them for appropriate workforce analysis.
6. Exclude negative-pay corrections from role-level compensation averages where they could distort results.

---

## 📂 Project Structure

```text
Cook-County-Payroll-Analysis/
│
├── data/
│   └── county_payroll_clean.csv
│
├── python/
│   └── data_cleaning.ipynb
│
├── excel/
│   └── Cook_County_Payroll_Analysis.xlsx
│
├── report/
│   └── Cook_County_Payroll_Compensation_Report.docx
│
└── README.md
```

---

## 📊 Deliverables

* Cleaned payroll dataset
* Python data-cleaning workflow
* Excel EDA with PivotTables
* Payroll and compensation analysis
* Business insights and recommendations
* Final analytical report

---

## 👩‍💻 Skills Demonstrated

**Data Cleaning:** Python, Pandas, Excel Power Query
**Data Analysis:** Excel PivotTables, aggregation, segmentation, trend analysis
**Business Analysis:** Workforce analysis, compensation analysis, cost concentration, data quality assessment
**Data Quality:** Duplicate detection, missing-value checks, payroll anomaly identification
**Data Visualization:** Excel charts and analytical reporting
**Documentation:** Business questions, findings, recommendations, and GitHub project documentation
