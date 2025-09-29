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
<img width="415" height="199" alt="image" src="https://github.com/user-attachments/assets/31e201a7-6f47-46d3-94bf-fa6118c372ed" />


Running monthly sales totals using SUM() OVER (ORDER BY month ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) 
<img width="415" height="166" alt="image" src="https://github.com/user-attachments/assets/a5dbb0e9-9eeb-4d95-80cb-2548d932303b" />


Month-over-month growth — computed with LAG() (percentage change vs previous month).
<img width="415" height="150" alt="image" src="https://github.com/user-attachments/assets/f1aad5fc-39aa-4ee5-9163-6d9a77dc8259" />


Customer quartiles — NTILE(4) to partition customers into spend quartiles for market segmentation.
<img width="415" height="232" alt="image" src="https://github.com/user-attachments/assets/a12e1f4d-8b99-48cf-9245-2ea10cacc88d" />


3-month moving averages — AVG() OVER (ORDER BY sale_month ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) to smoothen short-term volatility.
    <img width="415" height="224" alt="image" src="https://github.com/user-attachments/assets/d87b51f2-ef97-412b-8ace-d697db6b6b44" />
        

5 — Results Analysis 

5.1 Descriptive — What happened?

The top 5 products per region show that Samsung dominatesthe market revenue, while accessories (chargers & earbuds) rank lowest.

Customer segmentation reveals 20% of customers (top quartile) account for 55% of lifetime revenue.


5.2 Diagnostic — Why did it happen?

High concentration of revenue in top quartile indicates heavy repeat purchase or a small set of business/corporate buyers.

5.3 Prescriptive — What next?

Inventory : Increase shelf space and stock for top-ranked phones in Kigali and Southern; keep a higher accessory buffer in Western outlets.

Marketing : Create a VIP program targeting top-quartile customers (personalized offers, trade-in discounts). Run aftersales services to turn potential customers into loyal customers.



