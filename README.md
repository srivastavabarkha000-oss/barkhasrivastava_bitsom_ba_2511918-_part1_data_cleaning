# barkhasrivastava_bitsom_ba_2511918-_part1_data_cleaning

# Retail Sales Data Cleaning and Validation

## Problem Summary

The retail company exported order-level sales data from multiple internal systems. The raw dataset contained several data quality issues including inconsistent text formatting, duplicate records, missing values, inconsistent dates, invalid discounts, calculation mismatches, and order status inconsistencies.

The objective of this project was to clean, validate, and prepare the dataset for business analysis while documenting every transformation and business rule applied.

---

# Dataset Description

The dataset contains retail order-level transaction records with customer, product, sales, shipping, and payment information.

### Main Fields

* Order ID
* Order Date
* Ship Date
* Customer Name
* Segment
* Region
* State
* City
* Category
* Sub Category
* Quantity
* Unit Price
* Discount
* Sales
* Cost
* Profit
* Ship Mode
* Payment Status
* Order Status

---

# Tools Used

* Microsoft Excel

  * Data Cleaning
  * Pivot Tables
  * Conditional Formatting
  * Data Validation
  * Charts

* Python

  * Pandas
  * NumPy

* Visual Studio Code / Jupyter Notebook

---

# Cleaning Steps Performed

## Text Cleaning

* Removed leading and trailing spaces.
* Removed multiple internal spaces.
* Removed unwanted special characters where applicable.
* Standardized capitalization using Proper Case.
* Standardized Category names.
* Standardized Ship Mode values.
* Standardized Payment Status values.
* Standardized Order Status values.

---

## Date Cleaning

* Converted Order Date into a consistent format.
* Converted Ship Date into a consistent format.
* Verified shipping dates against order dates.

---

## Duplicate Handling

* Identified duplicate records.
* Removed exact duplicate rows.
* Flagged duplicate Order IDs for manual review.

---

## Missing Value Handling

* Missing Region → replaced with **Unknown**.
* Missing Ship Mode → replaced with **Unknown**.
* Missing Discount → replaced with **0** only when all sales fields were available.

---

## Validation

* Checked for invalid discounts.
* Checked sales calculations.
* Checked profit calculations.
* Validated shipping dates.
* Applied business rules.
* Flagged invalid records.

---

# Business Rules Applied

| Business Rule                | Action Taken                                                                 |
| ---------------------------- | ---------------------------------------------------------------------------- |
| Missing Region               | Filled with **Unknown** and flagged                                          |
| Missing Ship Mode            | Filled with **Unknown** and flagged                                          |
| Missing Discount             | Replaced with **0** only when Quantity, Unit Price, and Sales were available |
| Negative Discount            | Flagged as invalid                                                           |
| Discount Above Allowed Range | Flagged as invalid                                                           |
| Cancelled Orders             | Excluded from completed sales summary                                        |
| Failed Payments              | Excluded from completed sales summary                                        |
| Refunded Orders              | Reported separately                                                          |
| Ship Date Before Order Date  | Flagged as invalid shipping record                                           |

---

# Summary of Data Quality Issues Found

The following issues were identified during data profiling:

* Duplicate records
* Duplicate Order IDs
* Missing Region values
* Missing Ship Mode values
* Missing Discount values
* Negative Discount values
* Discounts above the allowed business threshold
* Mixed date formats
* Ship Date earlier than Order Date
* Sales calculation mismatches
* Profit calculation mismatches
* Inconsistent text formatting
* Inconsistent Category names
* Inconsistent Payment Status values
* Inconsistent Order Status values

---

# Summary of Final Pivot Reports

The cleaned dataset was used to generate business summary reports including:

* Total Sales by Region
* Total Sales by Category
* Sales by Segment
* Monthly Sales Trend
* Profit by Category
* Profit by Region
* Order Status Summary
* Payment Status Summary
* Refunded Orders Summary
* Top Performing States and Cities

---

# Key Business Insights

* Office Supplies and Technology generated the highest sales revenue.
* A small number of invalid discounts and shipping records were identified and flagged for review.
* Cancelled orders and failed payments reduced completed sales totals and were excluded from final reporting.
* Refunded transactions were summarized separately to improve financial reporting accuracy.
* Standardizing text fields significantly improved the quality of pivot tables and business reports.
* Data cleaning improved consistency, reduced duplicate records, and enhanced overall reporting reliability.

---

# Assumptions and Limitations

## Assumptions

* Maximum allowed discount was assumed to be **50%**.
* Missing Region values were replaced with **Unknown**.
* Missing Ship Mode values were replaced with **Unknown**.
* Missing Discount values were treated as **0** only when all required sales fields were available.
* Cancelled orders and failed payments do not contribute to completed sales.

## Limitations

* Conflicting duplicate Order IDs require manual investigation.
* Some business rules (such as maximum discount percentage) were assumed because they were not explicitly provided.
* Sales and profit validation depends on the availability of complete numeric fields.
* Flagged records should be reviewed before production reporting.

---

# Screenshots Included

The project submission includes screenshots of:

* Original Dataset
* Cleaned Dataset
* Excel Cleaning Process
* Duplicate Removal
* Text Standardization
* Date Cleaning
* Business Rule Validation
* Pivot Tables
* Charts and Dashboard
* Quality Report
* Cleaning Log

---

# Project Outcome

The final dataset is clean, validated, and analysis-ready. Business rules have been applied consistently, data quality issues have been documented, and summary reports have been prepared to support business decision-making.
