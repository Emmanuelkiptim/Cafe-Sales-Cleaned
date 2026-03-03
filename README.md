````markdown
# Cafe Sales Data Cleaning Project

## Overview

This project focuses on cleaning and preparing a **dirty cafe sales dataset** for analysis and reporting.

The raw dataset contained:
- Duplicate records  
- Missing values  
- Incorrect entries (`UNKNOWN`, `ERROR`)  
- Wrong data types  
- Inconsistent item pricing  
- Outliers in numeric columns  

After a structured data cleaning process using **Python (Pandas & NumPy)**, the dataset was transformed into a clean, analysis-ready file:

`Clean_Cafe_Sales.csv`

---

## Project Motivation

Real-world datasets are rarely clean. Before performing analysis, visualization, or machine learning, the data must be:

- Accurate  
- Consistent  
- Properly formatted  
- Free from extreme anomalies  

This project demonstrates practical data cleaning techniques used in real-world data analytics workflows.

The cleaned dataset can now be used for:
- Sales trend analysis  
- Revenue forecasting  
- Customer purchasing behavior analysis  
- Business intelligence dashboards  

---

## Tools & Technologies

- **Python**
- **Pandas** – Data cleaning & transformation  
- **NumPy** – Numerical operations  
- **Matplotlib** – Data visualization  
- **Seaborn** – Statistical data visualization  

---

## Data Cleaning Workflow

### Import Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
````

---

### Load Dataset

```python
df = pd.read_csv('dirty_cafe_sales.csv')
```

---

### Handle Missing & Incorrect Values

* Replaced `UNKNOWN` and `ERROR` with `NaN`
* Removed duplicate records
* Standardized categorical values

---

### 4️⃣ Correct Data Types

* `Transaction Date` → `datetime64[ns]`
* `Quantity` → `Int64`
* `Price Per Unit` → `float`
* `Total Spent` → `float`

---

### Missing Value Treatment

* Forward fill (`Item`)
* Mean imputation (`Quantity`)
* Standardized item prices using dictionary mapping
* Recalculated `Total Spent = Quantity × Price Per Unit`
* Backward fill (`Payment Method`, `Location`, `Transaction Date`)

---

###  Outlier Detection & Treatment

Used the **Interquartile Range (IQR) method** to detect outliers in:

* `Quantity`
* `Price Per Unit`
* `Total Spent`

Extreme values in `Total Spent` were capped to reduce skewness.

---

### Export Clean Dataset

```python
df.to_csv('Clean_Cafe_Sales.csv', index=False)
```

---

##  Dataset Description

| Column Name      | Description                                  |
| ---------------- | -------------------------------------------- |
| Transaction ID   | Unique sale identifier                       |
| Item             | Product sold (Coffee, Juice, Sandwich, etc.) |
| Quantity         | Number of items purchased                    |
| Price Per Unit   | Standardized item price                      |
| Total Spent      | Quantity × Price Per Unit                    |
| Payment Method   | Cash, Card, etc.                             |
| Location         | Store branch location                        |
| Transaction Date | Date of purchase                             |

---

##  Visualizations Included

* Boxplots for outlier detection
* Frequency distributions for:

  * Items
  * Locations
  * Payment Methods

---

##  How to Run the Project

### 1️ Clone the repository

```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

### 2️ Install dependencies

```bash
pip install numpy pandas matplotlib seaborn
```

### 3️ Run the cleaning script

```bash
python clean_cafe_sales.py
```

### 4 Output file

The cleaned dataset will be generated as:

```
Clean_Cafe_Sales.csv
```

---

## Final Output

✔ Cleaned
✔ Outliers handled
✔ Ready for analysis or machine learning

---

## Author

**Emmanuel Towett Kiptim**
Software Developer | Data Analyst

GitHub: [https://github.com/kiptimemmanuel](https://github.com/Emmanuelkiptim)

If you found this project useful, feel free to star the repository!
