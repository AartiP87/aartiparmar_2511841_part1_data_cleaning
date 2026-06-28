# aartiparmar_2511841_part1_data_cleaning

# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Problem Summary

The retail company exported order-level sales data from multiple internal systems. The raw dataset contained several data quality issues, including inconsistent text formatting, missing values, duplicate records, invalid discounts, date problems, and calculation mismatches. The objective of this project was to clean and validate the data, apply business rules, and prepare an analysis-ready dataset with summary reports for business review.

---

# Dataset Description

* **Dataset Name:** `raw_orders.xlsx`
* **Cleaned Dataset:** `cleaned_orders.xlsx`
* **Final Records:** 912
* **Final Columns:** 42
* **Data Includes:**

  * Customer information
  * Product categories and sub-categories
  * Order and shipping details
  * Sales, cost, profit, and discount information
  * Payment and order status

---

# Tools Used

* Microsoft Excel
* Excel Formulas (`TRIM`, `SUBSTITUTE`, `PROPER`, `IF`, `COUNTIF`, `DATEDIF`, `TEXT`, `YEAR`)
* Pivot Tables
* Conditional Formatting
* Filters and Sorting

---

# Cleaning Steps Performed

1. Preserved the original dataset in `raw_orders.xlsx`.
2. Standardized text fields by removing extra spaces and fixing case inconsistencies.
3. Cleaned and standardized date formats.
4. Created `shipping_delay_days`.
5. Identified and handled duplicate records.
6. Filled missing values where business rules allowed.
7. Validated discounts and flagged invalid records.
8. Created calculated columns:

   * `cleaned_discount`
   * `calculated_sales`
   * `calculated_profit`
   * `profit_margin`
   * `shipping_delay_days`
   * `order_month`
   * `order_year`
   * `data_quality_flag`
9. Created data quality reports and pivot summaries.

---

# Business Rules Applied

* Missing `region` → Filled with **Unknown**
* Missing `ship_mode` → Filled with **Unknown**
* Missing `discount` → Treated as **0** when other sales fields were valid.
* Negative discounts → Flagged as invalid.
* Cancelled orders → Excluded from completed sales analysis.
* Failed payments → Excluded from completed sales analysis.
* Refunded orders → Reported separately.
* Ship dates earlier than order dates → Flagged as invalid.

---

# Summary of Data Quality Issues Found

| Issue                         | Count |
| ----------------------------- | ----: |
| Missing Region                |    25 |
| Missing Ship Mode             |    21 |
| Missing Discount              |    18 |
| Exact Duplicate Rows          |    20 |
| Duplicate Order IDs           |    12 |
| Negative Discounts            |    15 |
| Invalid Shipping Records      |    21 |
| Cancelled Orders              |   145 |
| Failed Payments               |    69 |
| Refunded Orders               |    71 |
| Sales Calculation Mismatches  |    93 |
| Profit Calculation Mismatches |    40 |

**Final Data Quality Status**

* Clean Records: **891**
* Flagged Records: **21**
* Total Records: **912**

---

# Summary of Final Pivot Reports

The following pivot reports were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded, Cancelled, and Failed Orders by Region
6. Monthly Sales Trend

---

# Key Business Insights

* Most records (891 out of 912) passed all validation checks and are suitable for analysis.
* A significant number of orders were cancelled (145), which may indicate operational issues.
* Failed payments (69) and refunds (71) should be monitored to improve revenue quality.
* Sales and profit calculation mismatches suggest possible source system errors.
* Missing and inconsistent data highlights the need for stronger data entry controls.

---

# Assumptions and Limitations

## Assumptions

* Missing discounts can be treated as 0 if all other sales information is valid.
* Duplicate order IDs require manual business review before removal.
* Flagged records were retained for audit purposes.

## Limitations

* Some calculation mismatches may originate from source systems and cannot be corrected through cleaning alone.
* Certain duplicate records require business confirmation before any deletion.
* The project relies on the accuracy of the source data provided.

---

# Screenshots Included

The repository contains the following screenshots:

* `raw_data_preview.png`
* `cleaned_data_preview.png`
* `pivot_summary_1.png`
* `pivot_summary_2.png`

These screenshots provide evidence of the raw dataset, cleaned dataset, and final pivot reports.

---

# Conclusion

The dataset has been successfully cleaned, validated, and transformed into an analysis-ready format. The final outputs provide reliable information for business reporting, performance monitoring, and decision-making.

