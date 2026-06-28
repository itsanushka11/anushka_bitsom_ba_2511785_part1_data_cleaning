# anushka_bitsom_ba_2511785_part1_data_cleaning
# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Problem Summary

This project focuses on cleaning, validating, and preparing a retail orders dataset for business analysis using Microsoft Excel. The raw dataset contained inconsistent text formatting, mixed date formats, duplicate records, missing values, invalid discounts, and order status inconsistencies. The objective was to create a clean, analysis-ready dataset along with data quality reports and business summary reports.

---

## Dataset Description

* **Dataset Type:** Retail Order-Level Sales Data
* **Total Raw Records:** 932
* **Clean Records After Removing Exact Duplicates:** 912
* **File Format:** Microsoft Excel (.xlsx)

The dataset contains customer, product, sales, shipping, payment, and order-related information used for data cleaning and business reporting.

---

## Tools Used

* Microsoft Excel 2010
* Pivot Tables
* Excel Functions

  * `TRIM()`
  * `IF()`
  * `COUNTIF()`
  * `DATE()`
  * `YEAR()`
  * `TEXT()`
  * `ROUND()`
* Conditional Formatting
* Sorting & Filtering
* Data Validation
* Remove Duplicates

---

## Folder Structure

```text
part1_data_cleaning/
├── data/
│   ├── raw_orders.xlsx
│   └── cleaned_orders.xlsx
├── outputs/
│   ├── data_quality_report.xlsx
│   ├── pivot_summary.xlsx
│   └── cleaning_log.md
├── screenshots/
│   ├── raw_data_preview.png
│   ├── cleaned_data_preview.png
│   ├── pivot_summary_1.png
│   └── pivot_summary_2.png
└── README.md
```

---

## Cleaning Steps Performed

### Text Cleaning

* Removed leading and trailing spaces.
* Standardized text formatting.
* Corrected inconsistent values.
* Filled missing Region values with **Unknown**.
* Filled missing Ship Mode values with **Unknown**.

### Date Cleaning

* Converted mixed date formats into a consistent Excel date format.
* Validated Order Date and Ship Date.
* Calculated Shipping Delay Days.
* Flagged records with Ship Date earlier than Order Date.

### Duplicate Handling

* Removed **20** exact duplicate records.
* Identified duplicate Order IDs.
* Flagged conflicting duplicate Order IDs for manual review.

### Discount Validation

* Filled **18** missing discount values with **0** where applicable.
* Identified and flagged **15** negative discount values.
* Confirmed that no discount values exceeded the allowed range.

### Calculated Columns

Created the following calculated fields:

* `cleaned_discount`
* `calculated_sales`
* `calculated_profit`
* `profit_margin`
* `shipping_delay_days`
* `order_month`
* `order_year`
* `duplicate_flag`
* `profit_match`
* `data_quality_flag`

---

## Business Rules Applied

* Missing Region values were replaced with **Unknown**.
* Missing Ship Mode values were replaced with **Unknown**.
* Missing Discount values were replaced with **0** when valid.
* Negative Discount values were flagged as **Invalid**.
* Ship Date earlier than Order Date was flagged as **Invalid**.
* Cancelled Orders were excluded from completed sales summaries.
* Failed Payments were excluded from completed sales summaries.
* Refunded transactions were summarized separately.
* Duplicate Order IDs were retained and flagged for review.

---

## Data Quality Summary

| Metric                         | Result |
| ------------------------------ | -----: |
| Exact Duplicate Rows Removed   |     20 |
| Duplicate Order IDs Flagged    |     12 |
| Records Flagged for Review     |     24 |
| Missing Discount Values Filled |     18 |
| Negative Discount Values       |     15 |
| Cancelled Orders               |    145 |
| Failed Payments                |     69 |
| Refunded Payments              |     71 |

---

## Pivot Reports Created

The following Pivot Tables were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded, Cancelled, and Failed Orders by Region
6. Monthly Sales Trend

---

## Key Business Insights

* Several duplicate records were identified and handled appropriately.
* Missing values were standardized to improve data quality.
* Negative discounts and invalid shipping records were identified for further review.
* Cancelled, Failed, and Refunded transactions were separated from completed sales analysis.
* Cleaned data provides a reliable foundation for business reporting and decision-making.

---

## Assumptions

* Cost values represent the total cost per order.
* Missing discount values were treated as zero only when other sales fields were valid.
* Duplicate Order IDs with conflicting information require manual verification.

---

## Limitations

* Cleaning decisions were based only on the available dataset.
* Duplicate Order IDs were flagged rather than removed due to possible business significance.
* External source systems were not available for validation.

---

## Screenshots Included

* `raw_data_preview.png`
* `cleaned_data_preview.png`
* `pivot_summary_1.png`
* `pivot_summary_2.png`

---

## Conclusion

The dataset was successfully cleaned, validated, and transformed into an analysis-ready format. Data quality reports and pivot summaries were prepared to support business analysis and improve decision-making. The final cleaned dataset follows the required business rules and is suitable for further reporting and analytics.
