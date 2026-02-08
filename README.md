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
