
# FoodYum Grocery Store Sales Analysis

## Overview
A SQL (PostgreSQL) data cleaning and analysis project completed as part of 
the DataCamp Data Analyst Associate Practical Exam. The project uses a 
product dataset for FoodYum, a US-based grocery store chain, to clean 
messy data and answer key business questions around pricing and stock 
performance across product categories.

## Business Context
FoodYum sells items across five categories — Produce, Meat, Dairy, Bakery, 
and Snacks — and wants to ensure it stocks products across a range of 
prices in every category, so it can serve a broad range of customers as 
food costs rise.

## Objectives
1. Identify data quality issues (specifically a system bug affecting the 
   `year_added` field for 2022 entries)
2. Clean the dataset according to defined business rules
3. Analyze price ranges across product types
4. Flag high-performing Meat and Dairy products for closer review

## Process & Key Queries

**1. Data Quality Check**
Counted missing `year_added` values to quantify the impact of a known 
system bug — found 170 affected records.

**2. Data Cleaning**
Built a cleaned version of the dataset (`clean_data`) applying these rules:
- Missing `product_type` / `brand` → replaced with "Unknown"
- Missing `weight` / `price` → replaced with the overall median
- Missing `average_units_sold` → replaced with 0
- Missing `year_added` → replaced with 2022
- Missing `stock_location` → replaced with "Unknown"
- Original table left untouched; cleaning done via CTEs and conditional logic

**3. Price Range by Category**
Calculated `min_price` and `max_price` for each product type to understand 
how pricing spread varies — Meat had the highest overall range, Snacks 
the lowest.

**4. High-Performing Meat & Dairy Products**
Filtered Meat and Dairy products with `average_units_sold` greater than 10, 
returning 698 matching records for further review by the team.

## Tools Used
- **PostgreSQL** — data cleaning, transformation, and analysis
- **SQL** (CTEs, window functions, regex pattern matching, conditional 
  aggregation)

## Files
- `foodyum_analysis.sql` — full query set
- Practical exam brief (PDF)

## About
This project was completed as part of the DataCamp Data Analyst Associate 
certification, demonstrating SQL data cleaning, validation, and analytical 
querying skills.
