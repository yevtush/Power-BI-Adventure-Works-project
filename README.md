# Project description
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
# Dashboard description
## Page 1 — Executive Dashboard
<img width="1278" height="716" alt="image" src="https://github.com/user-attachments/assets/fc82eed1-ca81-4008-9e7b-c9d578a7feba" />

The Executive Dashboard serves as the top-level overview of the business, designed to give decision-makers a quick but comprehensive picture of company performance at a glance.

KPI Cards at the top display the four most critical business metrics — total revenue, profit, orders, and return rate — providing an immediate health check of the business without needing to dig deeper.

Weekly Revenue Chart tracks revenue over time from January 2020 to early 2022, with a trend line overlay to make the overall growth direction immediately visible despite short-term fluctuations. This is essential for spotting seasonal patterns and evaluating whether the business is on an upward trajectory.

Orders by Category breaks down order volume across Accessories, Bikes, and Clothing, helping identify which product lines drive the most customer activity — useful context for inventory and marketing decisions.

Product Performance Table provides a granular view of individual products, showing total orders, revenue, and return rate side by side. This allows quick identification of both top-selling products and potential quality issues flagged by elevated return rates.

Monthly KPI Cards for revenue, orders, and returns each include a comparison to the previous month, making it easy to assess short-term momentum at a glance.
Slicers for date range, country, and product category allow the entire page to be filtered interactively, making the dashboard relevant for different regions, time periods, or product lines without switching pages.
## Page 2 — Geographic Sales Map
<img width="1282" height="713" alt="image" src="https://github.com/user-attachments/assets/06fc8374-3a36-40f0-8369-85d465766a44" />

The Geographic Sales Map provides a spatial view of AdventureWorks' global order distribution, making it easy to understand where the business has the strongest market presence.

The bubble map plots sales territories across three regions — Europe, North America, and the Pacific — with bubble size proportional to total orders. This allows instant visual identification of the highest-volume markets without reading through tables of numbers.

At the top, three region buttons (Europe, North America, Pacific) act as interactive filters, zooming the view to the selected region for a more focused analysis. This is a cleaner and more intuitive navigation solution compared to a traditional dropdown slicer.
## Page 3 — Product Detail
<img width="1276" height="717" alt="image" src="https://github.com/user-attachments/assets/5f7cecd7-ed27-45be-920c-028f59855dfe" />

The Product Detail page provides a deep-dive view into the performance of an individual product. It is accessed via drill-through from the product table on the Executive Dashboard page.

A card visual at the top displays the currently selected product name, so it is always clear which product is being analyzed. A country slicer allows further filtering to compare product performance across different markets.

Three gauge charts display actual vs. target values for orders, revenue, and profit. Gauges are particularly effective here because they communicate not just raw performance numbers but also how close the product is to meeting its targets — something a plain KPI card cannot convey as intuitively.

The Profit Trend chart tracks monthly profit over time, revealing whether the product's profitability is growing, stable, or declining. The Return Trend chart monitors return volumes over the same period, which is important for flagging potential product quality or customer satisfaction issues before they escalate.
