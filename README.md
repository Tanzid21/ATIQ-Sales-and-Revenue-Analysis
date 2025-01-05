# ATLIQ-End-to-End Sales-and-Revenue-Analysis

# Problem Statement: 

In this project, we analyzed sales data for AtliQ Hardware, an India-based company specializing in supplying computer hardware and peripherals to various clients, such as Surge Stores and Nomad Stores, across the country. AtliQ Hardware operates from its head office in Delhi, with multiple regional offices spread throughout India.

The sales director of AtliQ Hardware faced significant challenges in tracking sales performance in a dynamically growing market. Despite having regional managers for North, South, and Central India, the reporting process was verbal, lacking factual and data-driven insights. This created frustration as overall sales were declining, yet regional managers provided incomplete or vague updates about their regions' performance. The lack of a centralized system for real-time sales tracking and analysis made it difficult to identify problem areas or opportunities for growth.

# Data Description:
To address these challenges, the objective was to develop a data visualization dashboard using Power BI. This tool would empower the sales director to access detailed, real-time insights into sales trends, revenue performance, customer behavior, and regional contributions. By leveraging data-driven decision-making, AtliQ Hardware aims to reverse declining sales, identify high-performing areas, and implement strategies to drive growth and improve business performance effectively.
The data for AtliQ Hardware's End-to-End Sales and Revenue Analysis encompasses multiple key datasets critical for understanding business performance across regions, customers, products, and timeframes. The primary dataset, sales.transactions, includes transaction-level details such as transaction IDs, market codes (e.g., Mark001 for Chennai), product codes, sales amounts, currencies (e.g., INR, USD), and order dates. Complementing this, the sales.customers table provides customer information, including unique customer IDs, names, and locations. Additionally, the sales.date table allows for time-based analysis with attributes such as date, year, month, and day. Product details, including product codes, names, and categories, add further granularity to the analysis. The data spans multiple years, covering transactions from 2019 and 2020, and includes market-specific data for cities like Chennai and Mumbai. Key preprocessing steps involved cleaning raw data, standardizing currencies, and resolving inconsistencies to ensure reliability for business intelligence activities. This comprehensive dataset enables insights into sales trends, revenue performance, customer behavior, and regional contributions, forming the foundation for a Power BI dashboard to support real-time, data-driven decision-making for AtliQ Hardware.


# Purpose
The primary goal of this project is to unlock previously unseen sales insights to support decision-making for the sales team. By automating data analysis and visualization, the project aims to significantly reduce the manual time spent on data gathering, enabling teams to focus on strategic activities.

# Stakeholders

Sales Director: Requires actionable insights to monitor and improve sales performance.
Marketing Team: Leverages sales data for targeted campaigns and customer engagement strategies.
Customer Service Team: Utilizes insights to enhance customer satisfaction and resolve issues effectively.
Data and Analytics Team: Responsible for maintaining and interpreting data to support informed decision-making.
IT: Ensures the smooth integration and functioning of the automated dashboard and data pipeline.

# Success Criteria

The dashboard successfully uncovers actionable sales order insights using the latest available data.
The sales team demonstrates improved decision-making capabilities, achieving a 10% cost savings in total expenditure.
Manual data gathering for sales analysis is eliminated, saving 20% of business time, which can then be reinvested into value-added activities.

# Analysis of different SQL statement on data base

1.To find of all customers records

SELECT * FROM sales.customers;

2.To find total number of customers

SELECT count(*) From sales.customers;

3.To find transactions for Chennai market (market code for chennai is Mark001

SELECT * FROM sales.transactions where market_code='Mark001';

4.To find distrinct product codes that were sold in chennai

SELECT distinct product_code FROM sales.transactions where market_code='Mark001';

5.To find transactions for Chennai market (market code for chennai is Mark002

SELECT * FROM sales.transactions where market_code='Mark002';

6.To find distrinct product codes that were sold in mumbai

SELECT distinct product_code FROM sales.transactions where market_code='Mark002';

7.To find transactions where currency is US dollars

SELECT * from sales.transactions where currency="USD";

8.To find transactions in 2020 join by date table

SELECT sales.transactions.*, sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020;

8.To find transactions in 2019 join by date table

SELECT sales.transactions.*, sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2019;

9.To find total revenue in year 2020,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";

10.To find total revenue in year 2019,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2019 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";

11.To find total revenue in year 2020, January Month,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="January" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

12.To find total revenue in year 2020, February Month,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="February" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

13.To find total revenue in year 2019, January Month,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="January" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

14.To find total revenue in year 2019, February Month,

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="February" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

15.To find total revenue in year 2020 in Chennai

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.market_code="Mark001";

16.To find total revenue in year 2020 in Mumbai

SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.market_code="Mark002";

Similarly, if we want different of any other particular city the market code of that city is used on the mysql workbench.


![image of tableue](https://github.com/user-attachments/assets/320e4ca2-5770-43c1-82f5-b002d118ff35)



# Recommendation
To address the challenges faced by AtliQ Hardware in tracking and improving sales performance, it is recommended to implement a centralized, automated data visualization dashboard using Power BI. This dashboard should integrate data from all relevant sources, such as sales transactions, customer records, product details, and date information, to provide real-time, actionable insights. The dashboard should allow the sales director and regional managers to track key metrics like revenue trends, regional performance, customer behavior, and high-performing products.

Additionally, efforts should be made to standardize currency values and resolve data inconsistencies to ensure accurate reporting. To further enhance decision-making, the dashboard should include filters for regions, timeframes, and product categories, enabling users to drill down into specific areas of interest. By leveraging these insights, AtliQ Hardware can identify underperforming regions, optimize sales strategies, and focus on high-growth opportunities. This will not only improve operational efficiency by eliminating manual data gathering but also help achieve measurable goals such as a 10% cost savings in expenditure and a 20% reduction in time spent on sales analysis. Ultimately, the adoption of this data-driven approach will empower AtliQ Hardware to reverse declining sales and drive sustainable business growth
