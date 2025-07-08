# Sales Exploratory Data Analysis

### PROJECT OVERVIEW
This project explores a company's sales data to uncover trends, top products, customer behavior, and revenue patterns. It uses visualizations and summary statistics to generate insights that can support data-driven business decisions with pure python.

### Data Source
all_data: The primary data set used for this analysis is the "all_data.csv" file. It contains very detailed information about each order made by the customers. The columns are namely OrderID, Product, Quantity Ordered, price Each, Order Date and Purchase Address of the customers.

### Tools
- Python
- Matplotlib

### Data Cleaning/Preparation
In this phase, I performed the following tasked:
  - Data importing and inspections
      - ``` python
              import pandas as pd
              df = pd.read_csv('all_data.csv')
              df.info()
        ```
  - Handling the duplicate values
      -  ``` python
              df.duplicated().sum()
              df.drop_duplicates(inplace = True)
         ```
  - Handling the null values
      -  ``` python
              df.isnull().sum()
              df= df.dropna(how='all')
         ```


### Exploratory Data Analysis
The EDA involve exploring the data to answer these key questions:
  1. what is the best month for sales?
  2. which city has the max order?
  3. what time should we display advertisment to maximise for product?
  4. what product sold the most? and why?
  5. what product are most often sold together?

### Data Analysis
I did some datatype changing for some of the column to best fit the analysis and to avoid unforseenable errors. 
Since the data doesn't have a sales column. I create a sales column and use a function to split the month from the order date for later use'
  -  ``` python
        def month(x):
        return x.split('/')[0]
        df['Month'] = df['Order Date'].apply(month)
     ```


    
