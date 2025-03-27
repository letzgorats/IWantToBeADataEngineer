# Practical Exam: Insurance Upgrades

Travel Assured provides travel services to its customers. They are based in the United States.

Travel Assured provides everything from flights and hotel bookings to holiday insurance.

The sales team wants to sell upgrades to customers. So they can do this, it is vital that the data is clean, accurate and available for reporting.

They need your help to prepare some data before they start to run a new promotion.

**Database Schema**

The data you need is in the database named `insurance`.

![image](https://github.com/user-attachments/assets/7282323e-2a36-4614-95c9-f299978ff599)


<hr>

# Task 1 

The sales team want to use customer information to target their new promotion. But they think the data may not be clean enough to use. 

The table below shows what the sales team expect the data types and format to be.

Write a query that makes the `customers` table match the description provided, including identifying and cleaning all invalid values. 

-  Your output should be a DataFrame with the name 'clean_data'. Do not modify the `customers` table.
-  Note that the DataLab environment formats dates as YYYY-MM-DD-hh-ss-SSS. 

| Column Name       | Description                                                      |
|-------------------|------------------------------------------------------------------|
| customer_id         | Unique integer (set by the database, can’t take any other value) |
| location       | State names as a lower case string                              |
| age        | Integer value giving age of customer                              |
| registration_date          | Date of first registration with company                    |

```SQL
SELECT 
	public.customers.customer_id, 
	LOWER(public.customers.location) AS location,
	CAST(TRIM(REPLACE(public.customers.age,'Years','')) AS INTEGER) AS age,
	TO_CHAR(public.customers.registration_date,'YYYY-MM-DD-hh-ss-SSS') AS registration_date
FROM public.customers
```
![image](https://github.com/user-attachments/assets/e2b7ec2d-e7d0-4ffe-9e2b-d8e75093586a)

<hr>

# Task 2

The sales team wants to run a promotion on upgrades to international travel insurance policies. 

They only want to send this promotion to customers who have an active, US policy type.

Write a query to provide the `customer_id` and `start_date` for eligible customers.

```SQL
SELECT public.sales.customer_id, public.policy.start_date
FROM public.policy JOIN public.sales 
USING (policy_id)
WHERE public.policy.policy_type='US' AND public.policy.active=True
```
![image](https://github.com/user-attachments/assets/35b99c61-b8f7-48b1-944f-e090e3dcbcab)

<hr>

# Task 3

After the promotion has been sent, the sales team will need to monitor the number of active policy holders by policy type who purchased an upgrade.

Write a query that returns the data for the sales team to monitor. Your output should include `policy_type` and `number_active` columns.

![image](https://github.com/user-attachments/assets/3e4c1ed5-bcd8-40cd-b5de-3a694fe41d52)

```SQL
SELECT policy_type, COUNT(*) AS number_active
FROM public.purchase JOIN public.sales
USING(purchase_id)
JOIN public.policy
USING(policy_id)
WHERE public.purchase.purchase_type = 'Upgrade' AND public.policy.active = True
GROUP BY policy_type
```
![image](https://github.com/user-attachments/assets/522a2c6f-14e3-4898-aeba-0ad73fe6def3)


