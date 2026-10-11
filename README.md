# CodeOrbit_DataCleaning

**CodeOrbit Tech — Data Science Internship | Task 1: Data Cleaning & Exploration with Pandas**

## Overview
This project loads a messy employee dataset (CSV) with pandas and cleans it step by step. It handles missing values, duplicate rows and incorrect data types, then calculates basic statistics and summarises every cleaning step in a short report.

## Project Structure
```
CodeOrbit_DataCleaning/
├── Task1_Data_Cleaning_Pandas.ipynb   # Main notebook (all steps + report)
├── employee_data.csv                  # Raw, messy dataset (63 rows)
├── employee_data_cleaned.csv          # Cleaned output (60 rows)
└── README.md
```

## Dataset
`employee_data.csv` has 8 columns:

| Column | Description |
|---|---|
| employee_id | Unique employee ID |
| name | Employee name |
| age | Age (contains invalid text and missing values) |
| city | City (inconsistent spelling/case, missing values) |
| department | Department (missing values) |
| salary | Salary stored as text with `$` and commas |
| join_date | Joining date stored as text |
| performance_score | Score from 2.5 to 5.0 (missing values) |

**Problems deliberately included:** 3 duplicate rows, missing values in 5 columns, wrong data types, invalid entries such as `N/A` and `thirty`, and messy city names such as `  bangalore ` and `MUMBAI`.

## Steps Performed
1. Import libraries
2. Load the CSV
3. Inspect the raw data (`shape`, `info`, `describe`)
4. Detect problems (missing values, duplicates, wrong types)
5. Clean the data:
   - Remove duplicate rows
   - Convert age, salary and performance_score to numbers, and join_date to datetime
   - Strip whitespace and standardise capitalisation in city and department
   - Fill missing numeric values with the **median**
   - Fill missing categorical values with the **mode**
6. Verify the cleaned data
7. Basic statistics: mean, median, min, max, std and value counts
8. Save the cleaned CSV
9. Print the cleaning summary report

## Results
- Rows: **63 → 60** (3 duplicates removed)
- Missing values: **0** after cleaning
- All columns have correct data types

## How to Run
**Option 1: Jupyter Notebook**
```bash
pip install pandas numpy jupyter
jupyter notebook Task1_Data_Cleaning_Pandas.ipynb
```
Then click **Kernel → Restart & Run All**.

**Option 2: Google Colab**
1. Upload the notebook and `employee_data.csv` to Colab.
2. Click **Runtime → Run all**.

> Keep `employee_data.csv` in the same folder as the notebook.

## Requirements
- Python 3.8+
- pandas
- numpy

## Key Learnings
- Always inspect data first with `info()`, `isnull()` and `duplicated()`.
- Clean on a copy so the original data stays untouched.
- The median is a robust way to fill missing numbers.
- Document every cleaning step so the work is reproducible.

## Author
**Name:** Veda Shivayogi Ramagondanahalli
**Internship:** CodeOrbit Tech — Data Science (1 Month)

---
*Project submitted as part of the CodeOrbit Tech Data Science Internship Program — [codeorbittech.in](https://www.codeorbittech.in)*
