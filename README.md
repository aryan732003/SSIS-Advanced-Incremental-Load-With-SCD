# SSIS Learning Series – Project 2: Advanced Incremental Load with SCD Handling

## Overview

Welcome to **Project 2** of my SSIS Learning Series! This project dives into building an advanced **Incremental Load** process with **Slowly Changing Dimensions (SCD)** in SSIS. The objective was to automate the loading of financial data from Excel to SQL Server, while accurately managing changes in data over time.

### Key Objectives:
- Implement an efficient **Incremental Load** process.
- Handle **SCD Types 1 and 2** to track and manage changes.
- Build a scalable and production-ready ETL pipeline.

## Key Features & Techniques:

### ✔️ Incremental Load Logic:
- Only **new or modified** records are processed, minimizing load time and optimizing performance.

### ✔️ Slowly Changing Dimensions (SCD Types 1 & 2):
- **SCD Type 1** (Changing Dimensions): Used **dynamic SQL** within the OLE DB Command to **update records in-place**.
- **SCD Type 2** (Historical Tracking): Maintained **historical changes** by adding **start_date** and **end_date** columns via the **Derived Column transformation**.

### ✔️ Data Transformations & Enhancements:
- Cleaned and **formatted date fields** to match SQL Server standards.
- **Created an additional table** in the SQL Server database to maintain a history of incremental loads.
- Integrated **validation and error handling** to ensure a robust ETL process.

## Project Walkthrough:

1. **SSIS Package**:  
   The main SSIS package is designed to extract data from an Excel file, perform transformations, and load it into SQL Server. It also handles SCDs using the following logic:
   - **SCD Type 1** updates existing records with changes.
   - **SCD Type 2** creates new records to preserve historical data.

2. **Excel Data Source**:  
   The source data in Excel contains financial data that will be loaded into SQL Server. You can find the sample data in the `Data/` folder.

3. **Database Schema**:  
   The project implements a financial database that logs changes to the data, maintaining a history of both current and historical values.

4. **Error Handling**:  
   The package includes built-in **error handling** to ensure that issues are logged and can be addressed.

## Screenshots and Diagrams

![SCD Diagram](screenshots/SCDDiagram.png)
![ETL Flow](screenshots/ETLFlow.png)

## Files:
- **SSIS_Package**: Contains the SSIS package file (`.dtsx`) used for the project.
- **Data**: Includes the sample Excel file with financial data for testing the SSIS package.
- **Logs**: If available, contains log files for ETL executions.

## Key Takeaways:
This project helped me deepen my understanding of:
- Handling **Incremental Loads** and **SCDs** using SSIS.
- Writing **dynamic SQL** to handle data updates efficiently.
- **Versioning and historical data management** in data warehousing.
- Building **production-ready ETL pipelines** that are both efficient and scalable.

## Future Work:
- **Multi-source Integration**: In Project 3, I'll explore integrating data from multiple sources into a unified ETL pipeline.
- **Real-time Data Processing**: Moving towards **real-time data processing** with SSIS.

## How to Run the Project:
1. **Download the project** by cloning this repository:
   ```bash
   git clone https://github.com/your-username/SSIS-Advanced-Incremental-Load-With-SCD.git
Open the SSIS package file in SQL Server Data Tools (SSDT).

Configure your connection strings to point to your SQL Server instance.

Execute the package to run the ETL process.

Contributing:
Feel free to fork this project and contribute by submitting issues or pull requests. If you have suggestions or improvements, feel free to open an issue or contribute directly.

License:
This project is licensed under the MIT License.

Tags:
SSIS, ETL, Data Engineering, SQL Server, Incremental Load, Slowly Changing Dimensions (SCD), Excel To SQL, Data Transformation, SCD Types 1 and 2

perl
Copy
Edit

### 4. **Upload Your Files:**
- **SSIS_Package**: Include your SSIS `.dtsx` package file here.
- **Screenshots**: Add images of your SSIS workflows, error handling, or package execution to the `screenshots/` folder.
- **Sample Data**: If possible, add a sample Excel file (like `FinancialData.xlsx`) to the `Data/` folder.
- **Logs**: If you have logs from the SSIS package execution, add them under `Logs/`.

### 5. **Commit and Push the Changes:**
Once your files are in place, commit them with a clear message:

```bash
git add .
git commit -m "Added SSIS Incremental Load project with SCD handling"
git push origin main
