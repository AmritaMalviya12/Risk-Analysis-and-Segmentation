# Risk-Analysis-and-Segmentation
(Churn Analysis & Customer Intelligence)

This project is a full churn analysis I built for a subscription-based (OTT-style) business, using Python and SQL. The idea was to actually behave like a data analyst working on a real retention problem — pull data from a database, clean it, build KPIs, find patterns, and turn all of that into insights someone in the business could act on.

The problem I was solving

In subscription businesses (think Netflix, Hotstar, Prime-type platforms), keeping existing customers is way more important than constantly acquiring new ones. So the goal here was to figure out:

Who is likely to churn (leave)
Why they're leaving — what behavior or signals show up before they cancel
When they usually leave — is there a "danger zone" in their subscription lifecycle
Tools & tech used
SQL (sqlite3) – to store and query the raw data
Python – for the entire analysis workflow
Pandas & NumPy – data cleaning, transformation, and feature engineering
Matplotlib & Seaborn – visualizations
PowerPoint – to present findings and insights in a business-friendly format
Data structure

The data was spread across three related tables in a database called customer_churn:

db_customer – customer demographics (name, country, state, gender, DOB, interests, pincode)
db_subscription – subscription details (plan type, contract type, monthly charges, cancellation date/reason, CLTV, churn score)
db_support – customer support history (complaints, escalations, CSAT scores)

All three tables are linked by customerid, which let me join them together in Python to get a full picture of each customer.

What I actually did (step by step)
Connected SQL to Python and pulled data from all three tables using pandas + sqlite3.
Cleaned the data — fixed data types, renamed columns, handled missing/null values, and ran basic quality checks.
Engineered new features — created calculated columns like customer tenure, churn flags, and revenue-related metrics.
Did exploratory data analysis (EDA) — used group-by, aggregations, and pivot tables to understand patterns across plan types, states, and contract types.
Built visualizations using Matplotlib and Seaborn to make the trends easy to see.
Calculated 20+ business KPIs, including:
Churn rate & retention rate
Churn by plan type and by state
ARPU (average revenue per user)
Average customer tenure
Revenue at risk (customers with high churn scores)
Escalation rate and average complaints per customer
Correlation between support escalations and churn
Summarized everything into insights and action items, the way you'd present findings to a business/growth team.
Key insights I found
Overall churn rate came out to 28.6%, meaning retention was around 71.4%
Most churn was concentrated in the Basic plan, which isn't a huge revenue concern on its own
Karnataka stood out as the most affected state, and churn spiked specifically in September 2024
Average customer tenure was around 1,451 days, with an ARPU of roughly ₹18.8
Out of total revenue of 395, churn was responsible for a loss of about 74, along with 2,047 in lost CLTV — around 18% revenue loss overall
The biggest finding: monthly-contract customers churned at 55.6%, compared to just 8.3% for annual-contract customers — almost 7x higher. This pointed toward contract type being a major churn driver, not just price or product issues.
Customers with support escalations churned disproportionately more than those without — support experience clearly played a role in whether someone stayed or left.
Action items that came out of this
Investigate what happened in Karnataka around September — pricing changes, complaints, or technical issues
Check if pricing was changed for the Basic plan around that time
Look into competitor movement, since at least one customer's churn was traced to switching providers
Prioritize outreach (email/SMS/calls) to customers flagged as High or Medium churn risk, based on their CLTV and complaint history
Consider a contract-migration strategy — nudging monthly subscribers toward annual plans, since annual customers churn far less
What this project taught me
How to work with relational data across multiple tables instead of a single flat file
Writing SQL queries and pulling that data directly into Python for analysis
Building meaningful KPIs instead of just running random EDA
Connecting technical findings (churn scores, correlations) to actual business decisions
Structuring an analysis so it's presentable — not just code, but a story someone can act on
