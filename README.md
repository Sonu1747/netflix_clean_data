# Data Cleaning and Preprocessing - Netflix Titles

This repository contains the results of Task 1, focusing on cleaning and preparing a raw dataset (Netflix Movies and TV Shows) for subsequent analysis and modeling. The entire process was conducted using Python (Pandas).

---

## 🚀 Project Files

| File Name | Description |
| :--- | :--- |
| `netflix_cleaning_script.ipynb` | The Jupyter Notebook containing the full code for data loading, inspection, cleaning, and transformation. (Alternatively, use a `.py` file). |
| `netflix_titles_cleaned.csv` | The final, clean dataset ready for analysis. |

---

## 🧹 Summary of Data Cleaning Changes

The raw dataset had issues including missing values, inconsistent formats, and unstructured column names. The following actions were taken to ensure data quality:

### 1. Handling Missing Values (Imputation and Deletion)

| Column | Missing Value Count (Initial) | Strategy Implemented | Outcome |
| :--- | :--- | :--- | :--- |
| `director` | 2634 (approx. 29.9%) | **Imputed** with the string `'Unknown'`. | No nulls remaining. |
| `cast` | 825 (approx. 9.4%) | **Imputed** with the string `'Unknown'`. | No nulls remaining. |
| `country` | 831 (approx. 9.4%) | **Imputed** with the **mode** (most frequent country). | No nulls remaining. |
| `date_added` | 10 (approx. 0.1%) | Rows were **dropped** to preserve data integrity due to the low count. | Final rows: 8790. |
| `rating`, `duration` | Very few (7 total) | Remaining rows with nulls were **dropped** for completeness. | Final rows: 8790. |

### 2. Standardization and Formatting

| Data Element | Initial State | Action Taken |
| :--- | :--- | :--- |
| **Column Headers** | Mixed case (e.g., `Date Added`) | Converted all to **snake\_case** (e.g., `date_added`). |
| **Data Type** | `date_added` was an `object` (string). | Converted to **`datetime64[ns]`** after stripping inconsistent white spaces. |
| **Text Consistency** | `country` names had inconsistent casing/spaces. | Applied `.str.strip()` and `.str.title()` for uniform formatting. |

---

## ✨ Final Dataset Status

The final dataset, `netflix_titles_cleaned.csv`, contains **8790 records** and **12 columns**, with **zero missing values** across all features and consistent data types, making it suitable for subsequent Exploratory Data Analysis (EDA) and modeling.
