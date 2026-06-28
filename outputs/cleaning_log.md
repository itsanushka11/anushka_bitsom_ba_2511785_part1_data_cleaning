# Cleaning Log

## Project

**Data Cleaning and Validation**

## Objective

The objective of this project was to clean, validate, and prepare the retail orders dataset for business analysis by applying data cleaning techniques, business rules, and data quality checks in Microsoft Excel.

---

## Issues Found

The following issues were identified in the raw dataset:

- Inconsistent text formatting in customer and product-related fields
- Leading and trailing spaces in text columns
- Missing values in Region, Ship Mode, and Discount
- Mixed date formats in Order Date and Ship Date
- Exact duplicate records
- Duplicate Order ID values with conflicting information
- Negative discount values
- Ship dates occurring before order dates
- Cancelled, Failed, and Refunded transactions requiring separate handling

---

## Cleaning Actions Performed

### Text Cleaning

- Removed extra spaces using `TRIM()`
- Standardized text formatting
- Corrected inconsistent category and field values
- Filled missing Region values with **Unknown**
- Filled missing Ship Mode values with **Unknown**

### Date Cleaning

- Converted mixed date formats into a consistent Excel date format
- Validated Order Date and Ship Date
- Created the `shipping_delay_days` column
- Flagged records where Ship Date occurred before Order Date

### Duplicate Handling

- Removed **20** exact duplicate records
- Identified **12** duplicate Order IDs
- Flagged **24** records for manual review instead of deleting them

### Discount Validation

- Filled **18** missing discount values with **0** where applicable
- Identified **15** negative discount values and flagged them as invalid
- No discount values greater than the allowed range were found

### Calculated Columns Created

- `cleaned_discount`
- `calculated_sales`
- `calculated_profit`
- `profit_margin`
- `shipping_delay_days`
- `order_month`
- `order_year`
- `duplicate_flag`
- `profit_match`
- `data_quality_flag`

---

## Business Rules Applied

- Missing Region values were replaced with **Unknown**
- Missing Ship Mode values were replaced with **Unknown**
- Missing Discount values were replaced with **0** when appropriate
- Negative Discount values were flagged as **Invalid**
- Ship Date earlier than Order Date was flagged as **Invalid**
- Cancelled Orders were excluded from completed sales analysis
- Failed Payments were excluded from completed sales analysis
- Refunded transactions were summarized separately
- Duplicate Order IDs were retained and flagged for review

---

## Assumptions Made

- Cost values represent the total order cost rather than cost per unit.
- Missing discount values were treated as zero only when other required sales fields were available.
- Duplicate Order IDs with conflicting information may represent legitimate business scenarios and therefore were not removed.

---

## Records Removed

- **Exact Duplicate Records Removed:** 20

---

## Records Flagged

- **Duplicate Order ID Records Flagged:** 24
- **Negative Discount Records Flagged:** 15
- **Invalid Shipping Records:** Ship Date earlier than Order Date
- Records with **Unknown** Region or Ship Mode were marked with a warning in the `data_quality_flag`.

---

## Limitations

- Business rules were applied based on the available dataset.
- Conflicting duplicate Order IDs require manual business verification.
- The cleaning process was performed using Microsoft Excel without external validation against source systems.

---

## Outcome

The dataset was successfully cleaned, validated, and transformed into an analysis-ready format. Data quality reports and pivot summaries were created to support business analysis and decision-making.