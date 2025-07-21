# Sales Exploratory Data Analysis

### PROJECT OVERVIEW
This project explores a company's sales data to uncover trends, top products, customer behavior, and revenue patterns. It uses visualizations and summary statistics to generate insights that can support data-driven business decisions with pure python.

### Data Source
all_data: The primary data set used for this analysis is the "all_data.csv" file. It contains very detailed information about each order made by the customers. The columns are namely OrderID, Product, Quantity Ordered, price Each, Order Date and Purchase Address of the customers.

<img width="1393" height="505" alt="Data Preview" src="https://github.com/user-attachments/assets/12659a8e-5c61-4876-b3cf-3b12371b997a" />

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
Below were some of the visualization to answer the above questions.
 1. what is the best month for sales?

    <img width="858" height="481" alt="Bar plot Sales by month" src="https://github.com/user-attachments/assets/a6ff15be-e7c8-4e62-9669-73681019a149" />

2. which city has the max order?

    <img width="818" height="530" alt="Barplot of Quantity" src="https://github.com/user-attachments/assets/67db2dae-ca14-4dc5-8096-4f24b99f8773" />

3. what time should we display advertisment to maximise for product?
    
    <img width="775" height="438" alt="Line graph" src="https://github.com/user-attachments/assets/c8e94e8a-b8b0-4234-b8d2-46d9d2d31fd9" />

 4. what product sold the most? and why?

    <img width="795" height="616" alt="BarPlot and line" src="https://github.com/user-attachments/assets/0bad7194-284d-4823-8ca4-cfaa91263393" />

5. what product are most often sold together?

   <img width="1150" height="405" alt="Pie Chart" src="https://github.com/user-attachments/assets/330e3177-a6d9-4791-acb1-bae6b797b8bd" />
### Insights & Takeaways
 - From the bar chart above we can conclude base on the data at hand that in Decemeber we have the highest sales.Decmebers has been quite favourable to the company
 - With the graphical representation above, we can conclude thst san francisco has the highest overall order.
 - Best Times to Advertise: To maximize orders, The Company should focus advertising efforts during the hours leading up to and during the peak order times. This       ensures the product is top-of-mind when customers are most likely to order.
    Why? The highest order volume occurs at 7 PM, and this window captures the after-work and dinner demand
 - The top selling is "AAA Battery". The top selling product seem to have a correlation with the price of the product. the cheaper the product the higher the           quantity ordered and vice versa
 - The first most paired orders are Google phone with USB-C charging cable, Iphone with Lightning charging cable, Google phone with Wired Headphones, Iphone            with Wired Headphones and Vareebadd phone with USB-C Charging Cable
 
