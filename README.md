# Sales Invoice Data Analysis & Preprocessing

This project focuses on **merging two invoice datasets**, performing **Exploratory Data Analysis (EDA)**, generating **business insights**, and applying **data preprocessing techniques** such as handling missing values, outlier detection, and standardization.

---

## 📌 Project Objectives

* Merge multiple invoice datasets into a single dataset
* Perform exploratory data analysis (EDA)
* Extract business insights such as revenue, top-selling items, and high-value invoices
* Handle missing values and outliers
* Standardize numerical features for further analysis or modeling

---

## 📂 Datasets

* **Files used:**

  * `i1.csv`
  * `i2.csv`
* The datasets are merged using an **outer join** to ensure no data loss.

```python
d = d1.merge(d2, how='outer')
```

---

## 🧰 Libraries Used

* `numpy`
* `pandas`
* `matplotlib`
* `scikit-learn`

Install required libraries if needed:

```bash
pip install numpy pandas matplotlib scikit-learn
```

---

## 🔍 Exploratory Data Analysis (EDA)

The following EDA steps are performed:

### Dataset Overview

* Shape of the dataset
* Data types and non-null counts
* Statistical summary
* Missing value count

```python
d.shape
d.info()
d.describe()
d.isna().sum()
```

---

### Invoice Analysis

* Unique invoice numbers
* Number of unique invoices
* Total revenue
* Average purchase value

```python
Average Purchase Value = Total Revenue / Number of Invoices
```

---

### Invoice-Level Aggregation

* Total bill amount per invoice
* Retrieval of a specific invoice total
* Identification of invoices above average bill value

---

## 📊 Product Insights

### Top 3 Items by Quantity Sold

* Grouped by item name
* Visualized using a bar chart

### Top 3 Items by Revenue

* Based on total sales value (`Final Total`)

---

## 📅 Date-Based Analysis

* Highest-value invoices on a specific date (`2023-09-14`)
* Grouping by invoice number and sorting by final total

---

## 📈 Data Visualization

* Bar chart for top 3 items by quantity sold
* Clear labels and titles for interpretability

---

## 🧹 Data Preprocessing

### 1. Handling Missing Values

* Numeric columns are filled with their **mean values**

```python
d[numeric_cols] = d[numeric_cols].fillna(d[numeric_cols].mean())
```

---

### 2. Outlier Detection

* Outliers identified using the **Interquartile Range (IQR)** method
* Applied on key numerical columns:

  * Price, Quantity, Sub Total, Discount, Tax, Final Total, Table No., Covers

---

### 3. Outlier Removal

* Rows containing outliers are removed from the dataset

---

### 4. Feature Standardization

* Numerical features are standardized using **StandardScaler**
* Mean = 0, Standard Deviation = 1

```python
StandardScaler()
```

---
