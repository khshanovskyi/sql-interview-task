## TASK 1
We have such query and we get the complaints that it is running too long:
```sql
SELECT c.id AS customer_id,
       c.first_name,
       c.last_name,
       c.email,
       a.id AS account_id,
       a.account_type,
       t.id AS transaction_id,
       t.transaction_type,
       t.amount,
       t.transaction_date,
       t.target_account_id,
       tc.first_name AS target_first_name,
       tc.last_name AS target_last_name
FROM customers c
         JOIN accounts a ON c.id = a.customer_id
         JOIN transactions t ON a.id = t.account_id
         LEFT JOIN accounts ta ON t.target_account_id = ta.id
         LEFT JOIN customers tc ON ta.customer_id = tc.id;
```
How can we get a comprehension of what is wrong with execution time?