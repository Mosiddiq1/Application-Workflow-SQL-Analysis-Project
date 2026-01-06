# Application Workflow – SQL Analysis Project
A project where I will be using my power BI dataset using SQL now to analyse the data and answer the objectives set by a manager.
## Project Objective

The objective of this project is to use **SQL** to analyse an application processing workflow and assess:

- Data quality and reliability  
- Operational performance  
- Payment health and outstanding risk  

The project is designed to simulate a real world analytics task where raw operational data must first be validated and cleaned before being used for reporting or analysis.

## Executive Summary

This analysis evaluated an end to end application processing workflow to identify operational bottlenecks, payment risks, and performance drivers.

The findings show that while the majority of applications are successfully completed and paid, a significant proportion remain outstanding, creating operational and financial risk. Processing delays are not primarily driven by payment status or applicant geography, but by application type, with restoration workflows consistently taking over twice as long as standard registrations.

Further investigation revealed a small number of long standing outstanding cases (over 500 days since submission), indicating abandoned or unclosed workflows rather than recent delays. These insights highlight clear opportunities for targeted process improvement and backlog reduction.

## Business Questions

As part of this analysis, the following business questions are addressed using SQL:

### Data Quality & Validation
- How many applications exist in the raw dataset?
- Are there duplicate application records?
- Which fields contain missing values?
- Are there identifiable outliers in age, payment amount, or processing time?

### Operational Performance
- What is the average processing time across applications?
- Which application types take the longest to process?
- Are international applications processed slower than UK applications?
- How many applications are incomplete or withdrawn?

### Payment Health
- How many applications are Paid, Pending, or Unpaid?
- What percentage of applications successfully complete payment?
- How much revenue has been collected (Paid only)?
- How many applications remain outstanding and require follow-up?

### Trends & Patterns
- How does collected revenue change over time?
- Are there differences in payment behaviour across years?
- Which application types contribute most to total revenue?

---

## Approach

The project follows a layered SQL approach:

1. **Raw Data Layer**  
   - CSV data is imported into a raw staging table without modification.

2. **Cleaned / Reporting Layer**  
   - Duplicate records are removed.
   - Data types are standardised.
   - Basic data quality checks are applied.
   - Cleaned views are created for analysis.

3. **Analysis Layer**  
   - SQL queries and views are written to answer the defined business questions.
   - KPIs and metrics are calculated directly in SQL.

This structure mirrors how SQL is commonly used in production analytics environments.

---

## Deliverables

- Raw staging table containing the original dataset  
- Cleaned SQL views for reporting  
- SQL queries answering key operational and payment questions  
- Reusable queries suitable for BI or reporting tools  

---

##  Why This Project Matters

This project demonstrates the ability to:
- Work with imperfect, real-world data  
- Validate and clean datasets using SQL  
- Translate business questions into analytical queries  
- Build a reliable data foundation for reporting and dashboards  

It complements the Power BI dashboard built on the same dataset, showcasing an end-to-end analytics workflow.

## ✅ Progress Summary (SQL)

The following steps have been completed as part of the SQL analysis workflow:

### Data Ingestion
- Imported the original CSV dataset into SQL Server as a raw staging table.
- Preserved all original records, including duplicates, nulls, and outliers, to reflect real-world data conditions.

### Data Validation
- Verified successful import with an initial row count of **825 records**.
- Performed sanity checks to confirm data integrity before analysis.

### Duplicate Detection
- Identified **26 duplicate records** based on `ApplicationID`.
- Confirmed that the majority of duplicates were identical.
- Differentiated between true duplicates and records with missing primary keys.

### Handling Missing Primary Keys
- Detected **2 records with NULL ApplicationID values** containing distinct data.
- Retained these records as data quality issues rather than assigning artificial identifiers.
- This approach reflects real-world data governance and auditability practices.

### Deduplication Logic
- Implemented deduplication using `ROW_NUMBER()` partitioned by `ApplicationID`.
- Retained the most recent record per application.
- Created a clean reporting view (`dbo.vw_Applications_Clean`) while leaving the raw table unchanged.

### Clean Data Layer
- Established a clean, reusable SQL view to serve as the foundation for all further analysis.
- This mirrors a layered SQL architecture commonly used in production analytics environments.
  
## Data Quality Handling
Data quality checks identified empty-string values used in place of missing data; these were handled explicitly in filtering logic to prevent distorted aggregations. The analysis highlighted that restoration workflows consistently take longer to process than standard registrations, while international applications show marginally higher average processing times, reflecting realistic operational complexity.

## Processing Time Analysis
Evaluated application processing performance by calculating average days to process across application types and applicant categories (UK vs International). Integer processing duration values were explicitly cast to numeric types to ensure accurate averaging and rounding.

## Payment Health Analysis
Analysed payment outcomes across Paid, Pending, and Unpaid applications.
Calculated payment completion rate, total collected revenue (Paid only), and outstanding application volume.
Identified that ~29% of applications remain financially incomplete, with the highest outstanding volume coming from high-throughput application types such as Student Registration and Fully Qualified.
Further analysis revealed a small number of long standing outstanding cases (>500 days), indicating potential abandoned or unclosed workflows rather than recent payment delays.


## Creater
 Omar Siddiq
