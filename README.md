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
