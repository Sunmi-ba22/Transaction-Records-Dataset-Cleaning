#  Data Cleaning Project: Business Financial Transactions Dataset

##  Overview

This project focuses on cleaning and preparing a raw business financial transactions dataset for accurate analysis and decision-making.

Real-world datasets are often messy containing missing values, inconsistencies, duplicates, and invalid records. This project demonstrates a structured approach to transforming such data into a reliable and analysis-ready format.

---

##  Objectives

The main goals of this project were to:

* Handle missing values appropriately
* Remove duplicate records
* Standardize inconsistent data formats
* Clean numeric columns (Price, Quantity, Amount)
* Address invalid values (e.g., negative transactions)
* Prepare a clean dataset for further analysis

---

##  Dataset Description

The dataset contains transactional records with features such as:

* Transaction ID
* Customer ID
* Product Name
* Quantity
* Price
* Total Amount
* Transaction Status
* Transaction Date

---

##  Data Issues Identified

During the cleaning process, the following issues were observed:

* Missing values across multiple columns
* Duplicate records
* Inconsistent formatting in categorical columns
* Currency symbols in numeric fields
* Negative values in **Price** and **Quantity**
* High percentage of missing values in the **Transaction Date** column

---

##  Data Cleaning Steps

### 1. Handling Missing Values

* Filled categorical missing values with `"Unknown"`
* Evaluated numerical columns before deciding on treatment
* Dropped columns with excessive missing data where appropriate

---

### 2. Removing Duplicates

* Identified and removed duplicate rows to ensure data integrity

---

### 3. Standardizing Data Formats

* Cleaned and unified categorical values (e.g., transaction status)
* Ensured consistency in text formatting

---

### 4. Cleaning Numeric Columns

* Removed currency symbols from the **Amount/Price** columns
* Converted values to proper numeric data types

---

### 5. Handling Negative Values

Negative values were identified in the **Price** and **Quantity** columns.

These were associated with:

* Pending transactions
* Incomplete transactions
* Possible cancellations or refunds

####  Decision:

For accurate sales-focused analysis, only **completed transactions with positive values** were retained.

```python
df_clean = df[
    (df['Quantity'] > 0) & 
    (df['Price'] > 0) & 
    (df['Transaction_Status'] == 'Completed')
]
```

---

### 6. Dropping Transaction Date Column

The **Transaction Date** column contained a high proportion of missing values.

* Dropping rows would lead to major data loss
* Imputing values could introduce inaccuracies

####  Decision:

The column was removed to preserve overall data quality.

---

### 7. Final Data Validation

After cleaning:

* Data types were verified
* Missing values were checked
* Summary statistics were reviewed

---

##  Final Output

A cleaned dataset was generated:

 **`cleaned_financial_transactions.csv`**

This dataset:

* Contains only valid, completed transactions
* Has no duplicates
* Uses consistent formatting
* Is ready for analysis or modeling

---

##  Key Takeaways

* Data cleaning is critical for reliable insights
* Understanding business context is essential when handling anomalies
* Not all “bad” data should be dropped,  decisions must be intentional

---


---

##  Tools & Technologies

* Python 
* Pandas
* NumPy
* Jupyter Notebook

---

##  Author

**Sunmisola Lawal**

 Data Scientist | Mathematics Graduate | Machine Learning Engineer

---

##  If you found this helpful

Feel free to star this repository and connect with me!
