# AdventureWorks Sales Analytics

## Project Overview
A full analytical deep-dive into 4 years of AdventureWorks sales data,
built to answer 5 core business questions about seasonality, trends,
margin drivers, category profitability, and discount impact.

## Business Questions Answered
- Is sales revenue seasonal?
- Are sales and profits growing year-over-year?
- Why does margin fluctuate?
- Which categories and products drive real profit?
- How do discounts affect profitability?

## Key Findings
- **Bikes** generate ~80% of total profit
- **Discounts above 5%** destroy margin — 30%+ discounts produce -306% avg margin
- **~29,000 lines** show negative profit with 0% discount → structural pricing issue
- **Accessories** have 50–60% margin — high growth opportunity
- **Q1 & Q4** are the strongest profit quarters

## Tools Used
- SQL Server (T-SQL)
- Microsoft Excel (charts & pivot tables)
- AdventureWorks 2022 database

## Project Structure
- `/sql` — Full SQL code with internal documentation
- `/docs` — External documentation and final presentation

## How to Run
1. Restore AdventureWorks2022 to SQL Server
2. Run `sql/adventureworks_analysis.sql` top to bottom
3. The script creates `dbo.General_Panel` view and all analysis queries