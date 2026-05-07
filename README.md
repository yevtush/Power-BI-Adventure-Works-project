# Projet description
End-to-end Power BI project covering data modeling, DAX measures, and interactive dashboard design. Based on the AdventureWorks dataset from the Maven Analytics Udemy course.
# Dataset
The dataset used in this project represents transactional data for AdventureWorks Cycles, a fictional global manufacturer and seller of cycling equipment and accessories.
The raw data consists of 8 CSV files which were imported and transformed in Power Query Editor. The tables fall into two categories:
Fact Tables
- Sales Data (2020, 2021, 2022) — order-level transaction records containing order date, stock date, order number, product key, customer key, territory key, and order quantity
- Returns Data — records of returned products including return date, territory, product, and return quantity
Dimension Tables
- Customer Lookup — customer demographics including name, birth date, gender, marital status, annual income, education level, and occupation
- Product Lookup — product details including product name, standard cost, and retail price
- Product Categories Lookup — top-level product category names
- Product Subcategories Lookup — subcategory names linking products to categories
- Territory Lookup — geographic sales territory data covering region and country
- Calendar Lookup — a continuous date table used to enable time intelligence calculations
# Data Model
The data model follows a snowflake schema, with the Sales and Returns fact tables at the center, connected to their respective dimension tables via one-to-many relationships. The product hierarchy is normalized across three separate tables — Products, Subcategories, and Categories — which is the characteristic that distinguishes it from a pure star schema.
All relationships were configured as single-directional, following best practices for Power BI data modeling to ensure predictable filter propagation and optimal report performance.
<img width="1181" height="617" alt="image" src="https://github.com/user-attachments/assets/8daa5155-e172-44ee-b044-21a3ca6e0704" />
