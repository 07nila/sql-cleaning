# 🧹 SQL Data Cleaning Project – Layoffs 2022 Dataset

This project focuses on **cleaning and preparing real-world layoff data** using structured SQL operations. The dataset was sourced from [Kaggle - Layoffs 2022](https://www.kaggle.com/datasets/swaptr/layoffs-2022) and the cleaning is performed entirely in **MySQL**.

---

## 🗂 Dataset

- Source: [Kaggle - Layoffs 2022](https://www.kaggle.com/datasets/swaptr/layoffs-2022)
- Table: `world_layoffs.layoffs`

---

## 🔧 Cleaning Steps Performed

### 1️⃣ Remove Duplicates
- Used `ROW_NUMBER()` to identify duplicates across all major columns.
- Deleted duplicate rows based on row numbers greater than 1.
- Ensured unique records were retained by creating and cleaning a staging table.

### 2️⃣ Standardize Data & Fix Errors
- Replaced blank values with `NULL`.
- Populated missing industries using self-joins based on company name.
- Standardized inconsistent values (e.g., `"CryptoCurrency"` → `"Crypto"`, `"United States."` → `"United States"`).
- Converted date strings to proper `DATE` format using `STR_TO_DATE()`.

### 3️⃣ Handle Null Values
- Retained `NULL` values for key columns (`total_laid_off`, `percentage_laid_off`, `funds_raised_millions`) to support meaningful EDA.
- Deleted rows where both `total_laid_off` and `percentage_laid_off` were null and unusable.

### 4️⃣ Drop Unnecessary Columns
- Removed temporary columns like `row_num` used for deduplication and staging logic.

---

## 📁 Project Structure

