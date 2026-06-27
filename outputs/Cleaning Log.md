#### Cleaning_log

###### List of Issues Found

* Leading/trailing spaces in text fields
* Multiple spaces between words
* Mixed text capitalization
* Inconsistent category and ship mode names
* Duplicate records
* Missing Region values
* Missing Ship Mode values
* Missing Discount values
* Negative Discount values
* Discounts above the allowed range
* Ship Date earlier than Order Date
* Cancelled orders
* Failed payments
* Refunded payments



##### Cleaning Actions Performed

* Removed extra spaces using trimming.
* Standardized text fields to Proper Case.
* Standardized category, ship mode, payment status, and order status values.
* Converted date columns to a consistent date format.
* Filled missing Region values with **Unknown**.
* Filled missing Ship Mode values with **Unknown**.
* Replaced missing Discount values with **0** only when all required sales fields were available.
* Created quality flags for records that violated business rules.
* Removed exact duplicate records.



##### Business Rules Applied

|Rule|Action|
|-|-|
|Missing Region|Filled with **Unknown** and flagged|
|Missing Ship Mode|Filled with **Unknown** and flagged|
|Missing Discount|Filled with **0** only if Quantity, Unit Price, and Sales were present|
|Negative Discount|Flagged as invalid|
|Discount Above Allowed Range|Flagged as invalid (assumed maximum 50%)|
|Cancelled Orders|Excluded from completed sales summary|
|Failed Payments|Excluded from completed sales summary|
|Refunded Orders|Saved in a separate summary|
|Ship Date Before Order Date|Flagged as an invalid shipping record|



##### Assumptions Made

* The maximum valid discount is **50%**.
* "Unknown" is an acceptable replacement for missing Region and Ship Mode values.
* Missing Discount values are replaced with **0** only when the remaining sales information is complete.
* Cancelled orders and failed payments do not contribute to completed sales.
* Refunded orders are reported separately rather than included in completed sales.

\---

##### Records Removed

* Exact duplicate records were removed.
* Duplicate Order IDs with different transaction details were retained for manual review.

\---

##### Records Flagged

Records were flagged for:

* Missing Region
* Missing Ship Mode
* Negative Discount
* Discount Above Allowed Range
* Invalid Shipping Record
* Missing Discount Filled

\---

##### Limitations

* Conflicting duplicate Order IDs require manual investigation.
* The maximum discount threshold (50%) was assumed because no business threshold was provided.
* Sales and profit validation depend on the availability of numeric fields.
* Flagged records should be reviewed before business reporting.

