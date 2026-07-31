# 📊 Online Retail Sales Dashboard – Power BI

An interactive **Power BI dashboard** developed to analyse online retail sales, customer behaviour, product performance, and geographical trends between **2009 and 2011**.

## Project Overview

This project transforms raw retail transaction data into an interactive business intelligence report using **Power Query, DAX, and dimensional data modelling**.

The report contains three dashboard pages:

1. **Executive Overview**
2. **Customer Analysis**
3. **Product Performance**

## Dashboard Features

- Total Sales
- Total Orders
- Total Customers
- Total Quantity Sold
- Average Order Value
- Monthly Sales Trends
- Top and Bottom Products
- Top Customers by Revenue
- Country-level Sales Analysis
- Interactive Year, Country, and Product filters
- Page navigation between dashboards

## Data Model

A star-schema model was created using:

- `FactSales`
- `DimProduct`
- `DimCustomer`
- `DimDate`
- `Measures Table`

The two yearly worksheets were cleaned and appended into a single transaction-level fact table.

## Tools and Technologies

- Power BI Desktop
- Power Query
- DAX
- Microsoft Excel
- Star Schema Data Modelling
- Data Visualisation
- Business Intelligence

## Dataset

The project uses the **Online Retail II** dataset from the UCI Machine Learning Repository.

The dataset contains more than one million transactions from a UK-based non-store online retailer between December 2009 and December 2011. It includes invoice, product, quantity, price, customer, date, and country information.

Dataset link:

https://archive.ics.uci.edu/dataset/502/online+retail+ii

## Dashboard Preview

### Executive Overview

![Executive Overview](Images/Online%20Retail%20Sales%20Dashboard/Executive%20Summary.png)

### Customer Analysis

![Customer Analysis](Images/Online%20Retail%20Sales%20Dashboard/Customer%20Overview.png)

### Product Performance

![Product Performance](Images/Online%20Retail%20Sales%20Dashboard/Product%20Performance.png)

## Key DAX Measures

```DAX
Total Sales =
SUM(FactSales[SalesAmount])
