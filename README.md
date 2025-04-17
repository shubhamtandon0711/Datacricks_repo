
├── README.md                 # Overview of the project and instructions  
├── macros/                   # Excel macro files for data cleaning and formatting  
├── data/                     # Input and cleaned supplier data (CSV format)  
├── outputs/                  # Processed results, visualizations, and reports  
├── notebooks/                # Databricks notebooks for running analysis  
├── scripts/                  # Python or automation scripts used in Databricks  
├── docs/                     # Documentation, including work instructions and guides  
  

```
Supplier Data Analysis Workflow
This repository contains all the resources and instructions required to streamline the analysis of supplier data using Databricks. It includes step-by-step guidance, macros, and scripts to ensure the data processing is efficient and standardized.

Purpose
The purpose of this workflow is to:

Consolidate supplier data received in different formats.

Clean and standardize the data for analysis.

Utilize Databricks for advanced analytics and insights.

Share actionable results with the Supplier Engineering Team.

Getting Started
Prerequisites
Before starting, ensure you have the following in place:

Email Access:

Access to the public inbox global.supplier@qiagen.com to receive supplier data in Excel format.

If access is unavailable, contact:

Tom Dilger: Tom.Dilger@qiagen.com

John Schmitt: John.Schmitt@qiagen.com

Folder Access:

Local and SharePoint folders for saving supplier files.

Contact Tom Dilger or John Schmitt for SharePoint folder permissions.

Excel Tools:

Basic knowledge of Power Query for data consolidation.

Access to macro-enabled Excel files:

Data Cleaning File for Supplier

Weidmann Data Cleaning File 01.04.xlsm

Databricks Access:

Permissions to upload and download data from Databricks File System (DBFS).

Ensure a valid Databricks license.

Process Overview
Step 1: Collect Supplier Data
Suppliers send data via email, typically at the start of the month.

Save all files to a designated local folder (e.g., April_2025_raw) and on SharePoint for backup.

For suppliers like Weidmann (who report at month-end), include their data in the next month's batch.

Step 2: Consolidate Data with Power Query
Combine all supplier data into a single Excel sheet:

Open a new Excel file.

Navigate to Data > Get Data > From File > From Folder.

Select the folder with the supplier files.

Use Combine and Transform to merge the files.

Remove unnecessary or extra columns introduced by suppliers.

Ensure the data format is consistent before proceeding.

Step 3: Clean Data Using Macros
Open the macro file Data Cleaning File for Supplier.

Copy the consolidated data and paste it into the template.

Run the macro (allsupplier_cleaned_data) to clean and standardize the data.

Deletes unnecessary columns and rows.

Formats dates in YYYY-MM-DD format.

Fills blank cells with default values (e.g., 0).

Adds new headers and adjusts column widths for readability.

Step 4: Add Additional Columns
Populate the following manually:

Internal Stock Level: Extracted from SAP and added via VLOOKUP.

Recommended Stock Level: Derived from the monthly forecast using XLOOKUP.

Step 5: Save Cleaned Data as CSV
Save the cleaned and updated file in CSV format:

File name example: SupplierData_Cleaned_April_2025.csv.

Store the file locally and on SharePoint for team accessibility.

Step 6: Upload Data to Databricks
Start the Databricks notebook and ensure it’s running.

Upload the cleaned CSV file to Databricks via DBFS Browser.

Update the widget with the new month’s name and run the analysis.

Download the processed results and share them with the team on SharePoint.

Handling Special Cases
Processing Weidmann Data
Download the raw data and save it in the designated folder.

Use Weidmann Data Cleaning File 01.04.xlsm to format it correctly:

Run the macro Macro_1_WDM_NoColumnDeletion.

Ensure columns like Reporting Date and Target Inventory Level are accurate.

Save the cleaned file alongside other suppliers’ data.

Scripts and Tools
Macro Files
Weidmann Data Cleaning Macro:

Prepares Weidmann data for compatibility with other supplier data.

All Supplier Cleaned Data Macro:

Cleans and standardizes data from all other suppliers.

Key Features
Auto-formatting of dates and headers.

Filling empty cells and handling invalid values.

Adding additional columns for analysis.

Best Practices
Always double-check the data after cleaning and before analysis.

Maintain backups of raw and processed files (both locally and on SharePoint).

Use consistent file naming conventions for easier tracking.

Contact Information
For assistance, reach out to:

Databricks Issues:

Clemens Mahlmeister: Clemens.Mahlmeister@qiagen.com

Emil Duong: Emil.Duong@qiagen.com

Adam Sulik: Adam.Sulik@contractor.qiagen.com

Supplier Data Queries:

John Schmitt: John.Schmitt@qiagen.com

Project Management:

Tom Dilger: Tom.Dilger@qiagen.com



