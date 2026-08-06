# Superstore Sales and Predictive Analytics Dashboard – Power BI

An interactive **Power BI Business Intelligence solution** developed to analyse Superstore sales performance, product profitability, customer behaviour, regional performance, discount impact, shipping efficiency, future sales trends, and predicted profit risk.

---

## Project Overview

A Superstore business operates in a highly competitive market and needs evidence-based insights into the products, regions, categories, customer segments, discount levels, and shipping methods it should prioritise or review.

This project transforms the original flat Superstore dataset into a structured analytical solution using **Power Query, a star-schema data model, DAX, Power BI forecasting, and Python-based predictive modelling**.

The completed solution includes:

- Data cleaning and transformation in Power Query
- Star-schema dimensional modelling
- Dynamic KPI and time-intelligence measures
- Interactive page navigation and reset controls
- Product, customer, regional, discount, and shipping analysis
- Monthly sales forecasting with a confidence interval
- Multiple Linear Regression for profit prediction
- Actual-versus-predicted profit comparison
- High-loss-risk transaction identification
- Dynamic business insight panels

---

## Business Objectives

The dashboard was designed to help the Superstore:

- Monitor overall sales, profit, orders, customers, quantity, and margin
- Identify the strongest and weakest products and sub-categories
- Compare performance across regions, states, and cities
- Evaluate customer and segment contribution
- determine where discounting supports sales or damages profitability
- Compare shipping modes and delivery performance
- Analyse historical sales trends and seasonal behaviour
- Forecast future monthly sales
- Predict profit and identify transactions with potential loss risk
- Support data-driven product, customer, pricing, regional, and operational decisions

---

## Dashboard Pages

### 1. Landing Page

The landing page introduces the project, business problem, objectives, analytical workflow, data model, dataset summary, and instructions for using the report. It also provides navigation buttons to every analytical page.

![Landing Page](Images/Superstore%20Dashboard/Landing%20Page.png)

### 2. Executive Overview

Provides a high-level summary of the Superstore's commercial and operational performance.

Main features:

- Total Sales
- Total Profit
- Profit Margin
- Total Orders
- Total Customers
- Average Order Value
- Average Delivery Days
- Year-on-Year Sales Growth
- Monthly Sales and Profit Trend
- Sales by Region
- Profit by Category
- Sales Contribution by Segment
- Dynamic Business Insights
- Interactive filters and reset button

![Executive Overview](Images/Superstore%20Dashboard/Executive%20Overview.png)

### 3. Product Performance

Examines category, sub-category, and individual product performance.

Main features:

- Product Sales and Profit KPIs
- Sales and Profit by Sub-Category
- Top 10 Products by Sales
- Bottom 10 Products by Profit
- Product Sales-versus-Profit Scatter Plot
- Detailed Product Performance Matrix
- Product-level Discount and Margin Analysis
- Dynamic Product Insights

![Product Performance]

### 4. Regional Analysis

Evaluates geographical performance across regions, states, and cities.

Main features:

- Regional Sales and Profit Comparison
- State Sales Map
- Top 10 States by Sales
- Bottom 10 States by Profit
- Regional Profit by Category Matrix
- City Sales-versus-Profit Analysis
- Detailed State Performance
- Dynamic Regional Insights

![Regional Analysis](Images/Superstore%20Dashboard/Regional%20Analysis.png)

### 5. Customer Analysis

Analyses customer contribution, purchasing behaviour, and segment performance.

Main features:

- Total Customers
- Sales per Customer
- Average Order Value
- Sales and Profit by Segment
- Top Customers by Sales
- Bottom Customers by Profit
- Customer Sales-versus-Profit Scatter Plot
- Detailed Customer Performance Matrix
- Dynamic Customer Insights

![Customer Analysis](Images/Superstore%20Dashboard/Customer%20Analysis.png)

### 6. Discount and Profitability

Evaluates how discounting influences sales, profit, margin, and transaction losses.

Main features:

- Average Discount
- Total Loss
- Loss-Making Orders
- Loss-Making Sales
- Profit by Discount Band
- Sales by Discount Band
- Discount-versus-Profit Scatter Plot
- Loss by Sub-Category
- Bottom 10 Products by Profit
- Category and Discount Profit Matrix
- Dynamic Discount Insights

![Discount and Profitability](Images/Superstore%20Dashboard/Discount%20and%20Profitability.png)

### 7. Shipping Analysis

Assesses delivery speed, ship-mode usage, and operational performance.

Main features:

- Average Delivery Days
- Sales by Ship Date
- Average Delivery Days by Ship Mode
- Sales and Profit by Ship Mode
- Order Distribution by Ship Mode
- Delivery Performance by Region
- Order-Date Sales versus Ship-Date Sales
- Regional Shipping Matrix
- Dynamic Shipping Insights

![Shipping Analysis](Images/Superstore%20Dashboard/Shipping%20Analysis.png)

### 8. Sales Forecasting

Uses monthly historical sales to analyse patterns and project future performance.

Main features:

- Latest-Year and Previous-Year Sales
- Latest-Year Sales Growth
- Average Monthly Sales
- Highest and Lowest Monthly Sales
- Historical Monthly Sales Trend
- Six-Month Sales Forecast
- 95% Forecast Confidence Interval
- Current versus Previous-Year Sales
- Month-on-Month Sales Growth
- Sales Trend by Category and Region
- Forecast Assumptions
- Dynamic Forecast Insights

![Sales Forecasting](Images/Superstore%20Dashboard/Sales%20Forecasting.png)

### 9. Predictive Analytics

Uses **Python-based Multiple Linear Regression** to predict transaction-level profit and identify loss risk.

Predictor variables include:

- Sales
- Quantity
- Discount
- Delivery Days
- Category
- Sub-Category
- Segment
- Region
- Ship Mode

Main features:

- Model R-Squared
- Mean Absolute Error
- Root Mean Squared Error
- Actual Profit
- Predicted Profit
- High-Risk Transaction Count
- Actual-versus-Predicted Profit Scatter Plot
- Predicted Risk Distribution
- Top Products by Prediction Error
- Risk by Category
- High-Risk Transactions Table
- Dynamic Predictive Insights

![Predictive Analytics](Images/Superstore%20Dashboard/Predictive%20Analytics.png)

---

## Data Preparation

The original Superstore file was imported into Power BI and transformed in **Power Query**.

Key preparation steps included:

- Correcting data types
- Removing completely blank rows
- Checking duplicate `Row ID` values
- Reviewing nulls and errors
- Trimming and cleaning text columns
- Creating `Delivery Days`
- Creating `Profit Status`
- Creating detailed `Discount Bands`
- Creating a composite `Location Key`
- Creating a numeric `Ship Mode Key`
- Creating reference queries for the fact and dimension tables
- Disabling load for the staging query

### Derived Columns

- `Delivery Days`
- `Profit Status`
- `Discount Bands`
- `Discount Band Sort`
- `Location Key`
- `Ship Mode Key`
- `Month Start`
- `Month Year Label`

---

## Data Model

The report uses a **star schema** with one central fact table and five dimension tables.

### Fact Table

- `Fact_Sales`

### Dimension Tables

- `DimCustomer`
- `DimProduct`
- `DimLocation`
- `DimShipMode`
- `DimDate`

### Supporting Tables

- `_Measures`
- `Profit_Predictions`

### Model Structure

```text
                         DimCustomer
                              |
DimDate --------------- Fact_Sales --------------- DimProduct
                              |
                         DimLocation
                              |
                         DimShipMode
                              |
                     Profit_Predictions
```

### Core Relationships

- `DimCustomer[Customer ID]` → `Fact_Sales[Customer ID]`
- `DimProduct[Product ID]` → `Fact_Sales[Product ID]`
- `DimLocation[Location Key]` → `Fact_Sales[Location Key]`
- `DimShipMode[Ship Mode Key]` → `Fact_Sales[Ship Mode Key]`
- `DimDate[Date]` → `Fact_Sales[Order Date]` — active
- `DimDate[Date]` → `Fact_Sales[Ship Date]` — inactive
- `Fact_Sales[Row ID]` → `Profit_Predictions[Row ID]`

Dimension relationships use one-to-many cardinality and single-direction filtering. The prediction table is linked by the unique `Row ID`.

---

## Core DAX Measures

The report includes more than 20 reusable measures, including:

- Total Sales
- Total Profit
- Total Quantity
- Total Orders
- Total Customers
- Profit Margin %
- Average Order Value
- Profit per Order
- Sales per Customer
- Average Discount %
- Average Delivery Days
- Total Loss
- Loss-Making Orders
- Loss-Making Sales
- Previous Year Sales
- Sales YoY %
- Previous Year Profit
- Profit YoY %
- Sales by Ship Date
- Average Monthly Sales
- Highest Monthly Sales
- Lowest Monthly Sales
- Monthly Sales Change %
- Latest Year Sales
- Previous Latest Year Sales
- Latest Year Sales YoY %
- Actual Profit
- Predicted Profit
- Prediction Difference
- Model R Squared
- Model MAE
- Model RMSE
- High Risk Transactions

Dynamic DAX measures were also created for the Executive, Product, Regional, Customer, Discount, Shipping, Forecast, and Predictive insight panels.

---

## Forecasting Method

The forecasting page uses Power BI's built-in time-series forecast.

Configuration:

- Monthly date axis
- Six-month forecast horizon
- 95% confidence interval
- Automatic or 12-month seasonality
- Continuous date axis
- Historical monthly sales as the input series

The forecast supports planning but does not account for future promotions, competitor activity, economic shocks, or supply-chain disruption.

---

## Predictive Modelling

The predictive model was developed in Python and executed through Power Query.

### Model

**Multiple Linear Regression**

### Target Variable

- `Profit`

### Evaluation Metrics

- R-Squared
- Mean Absolute Error
- Root Mean Squared Error
- Prediction Error
- Absolute Error

### Predicted Risk Groups

- High Loss Risk
- Moderate Loss Risk
- Profitable

The prediction results were returned to Power BI as a pandas DataFrame and connected to `Fact_Sales` through `Row ID`.

---

## Key Dashboard Features

- Interactive KPI cards
- Dynamic DAX measures
- Star-schema data model
- Power Query transformations
- Cross-filtering and cross-highlighting
- Synced slicers
- Page navigation menu
- Page-specific reset buttons
- Conditional formatting
- Dynamic business insight panels
- Monthly sales forecasting
- Python-based predictive modelling
- High-risk transaction analysis
- Drill-through-ready product detail design

---

## Technologies Used

- Microsoft Power BI Desktop
- Power Query
- DAX
- Microsoft Excel/CSV
- Python 3.12
- pandas
- scikit-learn
- matplotlib
- Star Schema Data Modelling
- Time-Series Forecasting
- Multiple Linear Regression
- Business Intelligence
- Data Visualisation

---

## Dataset

**Superstore Dataset**

The dataset contains transaction-level Superstore data, including order and shipping dates, customer information, geography, products, sales, quantity, discount, and profit.

### Dataset Fields

- Row ID
- Order ID
- Order Date
- Ship Date
- Ship Mode
- Customer ID
- Customer Name
- Segment
- Country
- City
- State
- Postal Code
- Region
- Product ID
- Category
- Sub-Category
- Product Name
- Sales
- Quantity
- Discount
- Profit

Dataset source:

https://www.kaggle.com/datasets/vivek468/superstore-dataset-final

## Business Insights Supported

The completed dashboard helps users:

- Identify high-sales and high-profit products
- Detect high-sales products with weak or negative margins
- Prioritise profitable regions, states, customers, and segments
- Locate loss-making products, customers, and geographical markets
- Evaluate the profitability of different discount bands
- Identify over-discounted products and categories
- Compare shipping speed with commercial performance
- Monitor monthly sales patterns and year-on-year growth
- Estimate future sales using historical trends
- Compare actual and predicted profit
- Identify high-loss-risk transactions requiring management review

---

## Author

**Srija Biswas**

If this project is useful, consider giving the repository a ⭐.
