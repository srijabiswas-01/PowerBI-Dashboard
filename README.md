# Power BI Analytics Dashboards

A portfolio of interactive Power BI projects covering retail performance, customer and product analysis, forecasting, profitability, operations, and predictive analytics.

## Projects

| Project | Focus | Main report |
| --- | --- | --- |
| Online Retail Sales Dashboard | Sales KPIs, customer behaviour, product performance, geographical trends, and sales forecasting | [`Online Retail Sales Dashboard.pbix`](Online%20Retail%20Sales%20Dashboard.pbix) |
| Superstore Sales and Predictive Analytics Dashboard | Sales and profit performance, regional and shipping analysis, discount impact, forecasting, and profit-risk prediction | [`Supermarket Sales Dashboard.pbix`](Supermarket%20Sales%20Dashboard.pbix) |

## Online Retail Sales Dashboard

This dashboard analyses more than one million transactions from a UK-based online retailer, covering December 2009 through December 2011.

### Dashboard pages

- Executive Summary with sales, orders, customers, quantity, average order value, monthly trends, and country performance
- Customer Overview with customer contribution, purchase behaviour, and geographic distribution
- Product Performance with top and bottom products, revenue contribution, and quantity sold
- Forecasting with historical monthly sales, projected sales, and confidence intervals

### Preview

![Online Retail Executive Summary](Images/Online%20Retail%20Sales%20Dashboard/Executive%20Summary.png)

Additional previews: [Customer Overview](Images/Online%20Retail%20Sales%20Dashboard/Customer%20Overview.png) | [Product Performance](Images/Online%20Retail%20Sales%20Dashboard/Product%20Performance.png) | [Forecasting](Images/Online%20Retail%20Sales%20Dashboard/Forecasting.png)

### Resources

- [Detailed project documentation](Online-Retail-Sales-Dashboard-README.md)
- [Source dataset](https://archive.ics.uci.edu/dataset/502/online+retail+ii)
- Local workbook: `Retail/online+retail+ii/online_retail_II.xlsx`

## Superstore Sales and Predictive Analytics Dashboard

This end-to-end business intelligence solution analyses transaction-level Superstore data and extends descriptive reporting with sales forecasting and Python-based profit-risk prediction.

### Dashboard pages

- Landing Page and Executive Overview
- Product Performance
- Regional Analysis
- Customer Analysis
- Discount and Profitability
- Shipping Analysis
- Sales Forecasting
- Predictive Analytics

The predictive model uses multiple linear regression to compare actual and predicted profit and classify potentially high-risk transactions. Model outputs include R-squared, mean absolute error, and root mean squared error.

### Preview

![Superstore Executive Overview](Images/Superstore%20Dashboard/Executive%20Overview.png)

Additional previews: [Product Performance](Images/Superstore%20Dashboard/Product%20Performance.png) | [Regional Analysis](Images/Superstore%20Dashboard/Regional%20Analysis.png) | [Customer Analysis](Images/Superstore%20Dashboard/Customer%20Analysis.png) | [Discount and Profitability](Images/Superstore%20Dashboard/Discount%20and%20Profitability.png) | [Shipping Analysis](Images/Superstore%20Dashboard/Shipping%20Analysis.png) | [Sales Forecasting](Images/Superstore%20Dashboard/Sales%20Forecasting.png) | [Predictive Analytics](Images/Superstore%20Dashboard/Predictive%20Analytics.png)

### Resources

- [Detailed project documentation](Supermarket_Sales_README.md)
- [Source dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- Local dataset: `Supermarket Sales/Superstore Data.csv`

## Technical Approach

Across the two projects, the solutions demonstrate:

- Data cleaning and transformation with Power Query
- Star-schema dimensional modelling
- Reusable DAX measures and time intelligence
- KPI cards, slicers, navigation, conditional formatting, and dynamic insights
- Customer, product, regional, profitability, and trend analysis
- Time-series sales forecasting with confidence intervals
- Python, pandas, and scikit-learn integration for predictive modelling

## Tools and Technologies

- Microsoft Power BI Desktop
- Power Query
- DAX
- Microsoft Excel and CSV
- Python, pandas, scikit-learn, and matplotlib
- Star-schema data modelling
- Time-series forecasting and multiple linear regression

## Author

**Srija Biswas**
