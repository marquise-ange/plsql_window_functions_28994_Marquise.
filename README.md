# plsql_window_functions_28994_Marquise.

 ### Step 1: Problem Definition:
## Business Context:
The business is a tour and travel company operating in Rwanda, offering different tour packages to customers across multiple regions. The company manages customer information, tour packages, and booking transactions through a centralized database.

## Data Challenge
The company collects large amounts of booking and sales data but struggles to analyze it effectively. Management finds it difficult to identify top-performing tour packages, understand customer purchasing behavior, and track sales performance trends over time using raw transactional data alone.

## Expected Outcome
The analysis aims to provide clear insights into tour package performance, customer value, and sales trends. These insights will support management in making informed decisions related to marketing strategies, customer targeting, and revenue optimization.

### step 2:Success Criteria:
1.	Identify the top five tour packages per region or quarter by ranking total revenue using the RANK() window function to highlight best-performing offerings.
2.	Calculate running monthly sales totals using SUM() OVER() to track cumulative revenue growth over time.
3.	Analyze month-over-month sales growth by comparing current and previous month revenues using LAG() or LEAD() functions.
4.	Segment customers into four quartiles based on total spending using the NTILE(4) function to identify high-value and low-value customer groups.
5.	Compute three-month moving average sales values using AVG() OVER() to smooth short-term fluctuations and reveal longer-term sales trends.

### Step 3: Database Schema Design:
<img width="1024" height="1024" alt="ER Diagram" src="https://github.com/user-attachments/assets/c5fd3380-18a3-413a-8e41-8574541fa4b4" />

 

### Step 4: Part A — SQL JOINs Implementation:

## INNER JOIN – Retrieve bookings with valid customers and tours:


<img width="1164" height="382" alt="innerjoin" src="https://github.com/user-attachments/assets/5bd474aa-b21b-4fcc-bbb1-d4dea69eb74f" />

## 2. LEFT JOIN – Identify customers who have never made a booking:

<img width="635" height="293" alt="leftjoin" src="https://github.com/user-attachments/assets/98c2c51e-f389-47dc-91b6-288f1b6b6e4b" />

3. RIGHT JOIN – Detect tours with no bookings:

<img width="542" height="278" alt="rightjoin" src="https://github.com/user-attachments/assets/d7334296-bd56-417f-973f-03896b6d9841" /> 

4. FULL OUTER JOIN – Compare all customers and all tours (including unmatched records):

<img width="916" height="594" alt="fullouterjoin" src="https://github.com/user-attachments/assets/e6485f3c-5026-47f4-b237-58d327b220e6" />


5. SELF JOIN – Compare customers within the same city who booked the same tour:

   <img width="1171" height="383" alt="selfjoin" src="https://github.com/user-attachments/assets/fcf67f6a-a9fe-4d63-8d1b-b4dd76c8dcc2" />

  Interpretation:

🔗 The JOIN queries provide a complete view of customer and tour activity, connecting bookings with customer and tour details.

🚫 They identify inactive customers and underperforming tours, revealing opportunities for growth.

🎯 These insights help management make data-driven decisions to improve sales, target marketing campaigns, and optimize tour performance.

### step 5:Window Functions Implementation:
1. Ranking Functions — RANK(), ROW_NUMBER(), DENSE_RANK(), PERCENT_RANK():

<img width="826" height="348" alt="s1" src="https://github.com/user-attachments/assets/e560317c-a018-421b-9833-92f4699d3776" />

2. Aggregate Window Functions:

<img width="1037" height="326" alt="s2" src="https://github.com/user-attachments/assets/2c2f8a23-0a55-4b47-b9ac-b6dc6d04c254" />

3. Navigation Functions:

   <img width="1037" height="342" alt="s3" src="https://github.com/user-attachments/assets/29c3da87-7dc3-49d7-a250-555b7ecb611e" />

4.Distribution Functions:


<img width="641" height="307" alt="s4" src="https://github.com/user-attachments/assets/7ac67dbb-a608-41fa-bedb-204d499a8667" />

Interpretation:

📊 Customers are divided into four quartiles based on total spending, with the top-spending customers in the first quartile.

🎯 This segmentation helps management identify high-value clients and target them with special promotions or loyalty programs.

💡 Lower-spending quartiles highlight customers who may need marketing efforts to increase engagement and revenue.


### Step 7: Results Analysis:

1️ Descriptive — What happened?

📊 Top customers by total spending were identified: Marquise Ange leads with $1000, followed by Diana Prince ($500) and Bruce Wayne ($300).

🔗 Most bookings occurred in Kigali, with some regions like Musanze having fewer transactions.

💰 Running totals and moving averages show gradual growth in total booking revenue over the first two weeks of January 2026.

2️⃣ Diagnostic — Why did it happen?

🏙️ The majority of bookings are concentrated in Kigali because it is the capital and a popular tourist hub, attracting more customers.

🎯 Top-spending customers booked multiple tours or larger quantities, increasing their total revenue contribution.

🚫 Tours with no or few bookings (like some Musanze or Huye packages) indicate either low promotion, limited awareness, or scheduling mismatches.

3️⃣ Prescriptive — What should be done next?

🎁 Focus marketing campaigns and loyalty programs on high-value customers to maintain engagement and repeat bookings.

📣 Promote underperforming tours or less-booked regions via discounts, bundled packages, or regional campaigns to increase adoption.

📈 Monitor moving averages and month-over-month trends continuously to adjust tour offerings, pricing, and resource allocation.

Conclusion

In this assignment, I successfully designed a relational database for a tour company, created the necessary tables (customers, tours, bookings), and populated them with sample data. I implemented various SQL JOINs to analyze customer and tour activity, identifying valid bookings, inactive customers, and underperforming tours.

I also applied Window Functions (Ranking, Aggregate, Navigation, and Distribution) to gain deeper insights into customer spending, running totals, booking trends, and segmentation. Through this work, I demonstrated the ability to extract meaningful business insights from transactional data, providing actionable recommendations to improve marketing, customer engagement, and revenue optimization.

Overall, this project strengthened my practical SQL skills and analytical thinking, preparing me for more advanced database analysis tasks.

REFERENCE:
https://www.youtube.com/watch?v=2HiD24PQqr8

