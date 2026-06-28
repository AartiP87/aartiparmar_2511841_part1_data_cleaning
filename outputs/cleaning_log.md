# Cleaning Log

## Dataset Information

* File: `cleaned_orders.xlsx`
* Total Records: **912**
* Total Columns: **42**

---

## Issues Found

* Missing `region` values.
* Missing `ship_mode` values.
* Invalid and inconsistent date formats.
* Some ship dates occurred before order dates.
* Missing and invalid discount values.
* Duplicate `order_id` records.
* Sales and profit calculation mismatches.
* Inconsistent text formatting (extra spaces, case differences).

---

## Cleaning Actions Performed

* Standardized text fields using **TRIM**, **SUBSTITUTE**, and **PROPER** functions.
* Standardized all dates into a consistent format.
* Replaced missing `region` and `ship_mode` values with **Unknown**.
* Treated missing discounts as **0** where appropriate.
* Created calculated fields:

  * `cleaned_discount`
  * `calculated_sales`
  * `calculated_profit`
  * `profit_margin`
  * `shipping_delay_days`
  * `order_month`
  * `order_year`
  * `data_quality_flag`
* Flagged invalid and suspicious records for review.

---

## Business Rules Applied

* Missing `region` → **Unknown**
* Missing `ship_mode` → **Unknown**
* Missing discount → **0** (if other sales data was valid)
* Negative or excessive discounts → **Invalid**
* Cancelled orders → Excluded from completed sales analysis
* Failed payments → Excluded from completed sales analysis
* Refunded orders → Reported separately
* Ship date before order date → Flagged as invalid

---

## Records Removed

* No records were permanently deleted.
* Duplicate order IDs were retained and flagged for review.

---

## Records Flagged

* Invalid dates
* Invalid discounts
* Duplicate order IDs
* Sales/profit mismatches
* Shipping date issues

---

## Final Data Quality Summary

* **Clean Records:** 891
* **Flagged Records:** 21
* **Total Records:** 912

---

## Assumptions

* Missing discounts can be treated as 0 if other sales fields are valid.
* Duplicate order IDs require business review before removal.
* Flagged records were retained for audit purposes.

---

## Limitations

* Some calculation mismatches may originate from source system errors.
* Certain duplicate records require manual business validation.

---

## Conclusion

The dataset has been cleaned, validated, and prepared for analysis. Most records passed the quality checks and are suitable for reporting and dashboard creation.


