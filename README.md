# Application Workflow – SQL Analysis Project
A project where I will be using my power BI dataset using SQL now to analyse the data and answer the objectives set by a manager.
## Project Objective

The objective of this project is to use **SQL** to analyse an application processing workflow and assess:

- Data quality and reliability  
- Operational performance  
- Payment health and outstanding risk  

The project is designed to simulate a real world analytics task where raw operational data must first be validated and cleaned before being used for reporting or analysis.

---

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

## Creater
 Omar Siddiq
