
├── README.md                 # Overview of the project and instructions  
├── macros/                   # Excel macro files for data cleaning and formatting  
├── data/                     # Input and cleaned supplier data (CSV format)  
├── outputs/                  # Processed results, visualizations, and reports  
├── notebooks/                # Databricks notebooks for running analysis  
├── scripts/                  # Python or automation scripts used in Databricks  
├── docs/                     # Documentation, including work instructions and guides  
  

```
Supplier Data Analysis Workflow
📊 Streamline the processing and analysis of supplier data using Databricks!

This repository contains step-by-step guidance, tools, and scripts to make your data processing journey efficient and standardized.

🌟 Purpose
This workflow helps:
✅ Consolidate supplier data from various formats.
✅ Clean and standardize the data for seamless analysis.
✅ Leverage Databricks for advanced analytics and actionable insights.
✅ Share results effectively with the Supplier Engineering Team.

🚀 Getting Started
🔑 Prerequisites
Make sure you have:

📧 Email Access

Access to the public inbox: global.supplier@qiagen.com.

Contact for access:

Tom Dilger: Tom.Dilger@qiagen.com

John Schmitt: John.Schmitt@qiagen.com

📂 Folder Access

Permissions for local and SharePoint folders.

Contact: Tom or John for SharePoint access.

📊 Excel Tools

Familiarity with Power Query.

Access to macro files:

Data Cleaning File for Supplier.

Weidmann Data Cleaning File 01.04.xlsm.

💻 Databricks Access

Permissions for uploading and downloading files from DBFS.

Ensure a valid Databricks license.

📋 Workflow Overview
Step 1: Collect Supplier Data
📥 Suppliers send data at the start of the month.
✅ Save files to a local folder (e.g., April_2025_raw) and SharePoint for backup.
🔁 For suppliers like Weidmann (reporting at month-end), process their data in the next batch.

Step 2: Consolidate Data with Power Query
💡 Merge all supplier files into one Excel sheet:

Open a new Excel file.

Go to Data > Get Data > From File > From Folder.

Select the folder with supplier files.

Use Combine and Transform to merge the files.

Remove unnecessary columns added by suppliers.

Step 3: Clean Data Using Macros
🛠 Use Data Cleaning File for Supplier:

Copy consolidated data into the macro file.

Run the macro allsupplier_cleaned_data.

✨ What the Macro Does:

Deletes unnecessary columns/rows.

Formats dates in YYYY-MM-DD.

Fills blank cells with 0.

Adds headers and adjusts column widths.

Step 4: Add Additional Columns
📊 Manually add:

Internal Stock Level: Extracted from SAP using VLOOKUP.

Recommended Stock Level: Derived using XLOOKUP from forecasts.

Step 5: Save Cleaned Data as CSV
💾 Save the file in CSV format (e.g., SupplierData_Cleaned_April_2025.csv) and upload it to SharePoint for team access.

Step 6: Upload Data to Databricks
🚀 Process data with Databricks:

Start the Databricks notebook.

Upload the cleaned CSV via DBFS Browser.

Update the widget with the correct month’s name.

Run the analysis and download the results.

📌 Special Cases: Handling Weidmann Data
📂 Process raw Weidmann data using:

Weidmann Data Cleaning File 01.04.xlsm.

Run the macro Macro_1_WDM_NoColumnDeletion.

Ensure correct values in columns like Reporting Date.

Save the cleaned file alongside other suppliers’ data.

🛠 Tools and Scripts
Macro Files
Weidmann Data Cleaning Macro:
Standardizes Weidmann data.

All Supplier Cleaned Data Macro:
Cleans and formats all supplier data.

Key Features
✅ Auto-formatting of dates and headers.
✅ Replacing blank cells with default values.
✅ Adding additional columns for deeper analysis.

📝 Best Practices
✔ Double-check data after cleaning.
✔ Maintain consistent file naming conventions.
✔ Always back up files locally and on SharePoint.

📇 Contact Information
💻 Databricks Issues:

Clemens Mahlmeister: Clemens.Mahlmeister@qiagen.com

Emil Duong: Emil.Duong@qiagen.com

Adam Sulik: Adam.Sulik@contractor.qiagen.com

📧 Supplier Data Queries:

John Schmitt: John.Schmitt@qiagen.com

📂 Project Management:

Tom Dilger: Tom.Dilger@qiagen.com



