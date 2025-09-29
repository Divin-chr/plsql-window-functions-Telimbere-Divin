# plsql-window-functions-Telimbere-Divin
assignment

1.Business Scenario 
Business Context
This is a phone shop with multiple outlets across four regions (Kigali, Southern, Western, Eastern). What we need is better insight of the product performance, customer value, and trends in order to prioritize inventory, run targeted marketing, and manage promotions.

Data Challenge 
Sales data is scattered across outlets. Business needs to identify top products per region and quarter, monitor running monthly revenue, compute month-over-month growth, segment customers into quartiles by spend and smooth short-term volatility with 3-month moving averages using analytic/window functions. 

Expected Outcome
outputs: 

(1)top 5 products per region & quarter to prioritize stock and for promotions, 

(2)customer segments for targeted customers (top-quartile VIPs), 

(3)monthly and 3-month trends to accommodate prices and others.


2 — Success Criteria

Top 5 products per region/quarter — computed with RANK() 


Running monthly sales totals using SUM() OVER (ORDER BY month ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) 


Month-over-month growth — computed with LAG() (percentage change vs previous month).


Customer quartiles — NTILE(4) to partition customers into spend quartiles for market segmentation.


3-month moving averages — AVG() OVER (ORDER BY sale_month ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) to smoothen short-term volatility.
            

5 — Results Analysis 

5.1 Descriptive — What happened?

The top 5 products per region show that Samsung dominatesthe market revenue, while accessories (chargers & earbuds) rank lowest.

Customer segmentation reveals 20% of customers (top quartile) account for 55% of lifetime revenue.


5.2 Diagnostic — Why did it happen?

High concentration of revenue in top quartile indicates heavy repeat purchase or a small set of business/corporate buyers.

5.3 Prescriptive — What next?

Inventory : Increase shelf space and stock for top-ranked phones in Kigali and Southern; keep a higher accessory buffer in Western outlets.

Marketing : Create a VIP program targeting top-quartile customers (personalized offers, trade-in discounts). Run aftersales services to turn potential customers into loyal customers.



