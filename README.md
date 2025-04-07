# 📦 Supplier Data Analysis & Visualization in Databricks

Welcome to the **Supplier Data Analysis** repository! This project helps automate the process of collecting, cleaning, analyzing, and visualizing stock-related data from suppliers — all within the **Databricks** ecosystem.

---

## 📁 Project Overview

This project aims to streamline:
- 📨 Downloading data from suppliers (via SharePoint)
- 🧹 Preprocessing using Excel macros
- 🚀 Uploading cleaned data to Databricks
- 📊 Analyzing stock coverage and visualizing trends
- 📦 Making stock decisions based on QC/Recommended levels

---

## 🧩 Folder Structure

```bash
.
├── README.md
├── scripts/                  # PySpark and analysis scripts
├── macros/                   # Excel macro files
├── data/                     # Cleaned data (CSV)
├── outputs/                  # Visualizations or processed output
```

---

## 🔁 Workflow

### 1️⃣ Get Supplier Data

- Download the **March Weidmann** Excel from:
  `SharePoint > Supplier Coordination 06`

- Open the Excel and:
  - Delete old data and other sheets.
  - Paste the new data provided by supplier.
  - Run the macro `macro_weidmann_1`.

- Rename the second sheet to `Sheet1`.

---

### 2️⃣ Prepare for Databricks

- Open another Excel file: `Weidmann Data for Databricks`.
- Run the macro (button click).
- Data gets cleaned and reshaped.
- Copy the data and save it as a **new file**:
  `April_2025.xlsx` (Save locally & on SharePoint under supplier data folder)

---

### 3️⃣ Upload to Databricks

You can add data to Databricks in different ways:
- 📤 Upload via **Data > Add Data** (GUI)
- 📂 Use DBFS: `dbfs:/FileStore/filename.csv`
- 🧼 Programmatically with `dbutils.fs.cp` or API

---

### 4️⃣ Load & Process in Databricks

```python
file_path = "dbfs:/FileStore/april_trial_data.csv"
df = spark.read.csv(file_path, header=True, inferSchema=True)
```

- Clean columns:
```python
from pyspark.sql.functions import col, round

df = df.withColumn("average_consumption_per_day", 
                   round(col("Recommended Stock level at Supplier") / 66, 2))

df = df.withColumn("stock_coverage_in_weeks_for_supplier", 
                   round(col("QC released stock") / col("average_consumption_per_day") / 5, 2))
```

---

### 5️⃣ Analyze & Visualize

- Filter for top 20 parts with lowest average stock over 6 months
- Plot using matplotlib and seaborn:

```python
import matplotlib.pyplot as plt
import seaborn as sns

```

---

## 🛠️ Technologies Used

- 💾 Microsoft Excel (Macros for preprocessing, Power query to accumulate the data)
- 🧠 Databricks (Apache Spark engine)
- 🐍 PySpark (data manipulation)
- 📈 Matplotlib & Seaborn (visualization)

---

## 🙋‍♂️ Author

**Shubham Tandon**  
Werkstudent at QIAGEN

---

## 📬 Get in Touch

📧 Email: shubhamtandon777@gmail.com



