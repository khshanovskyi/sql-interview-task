## TASK 3
We have such main part of the query:
```sql
SELECT c.id                                 AS customer_id,
       c.first_name || ' ' || c.last_name   AS customer_name,
       c.email,
       a.id                                 AS account_id,
       a.account_type,
       t.id                                 AS transaction_id,
       t.transaction_type,
       t.amount,
       t.transaction_date,
       t.target_account_id,
       tc.first_name || ' ' || tc.last_name AS target_customer_name
FROM customers c
         JOIN accounts a ON c.id = a.customer_id
         JOIN transactions t ON a.id = t.account_id
         LEFT JOIN accounts ta ON t.target_account_id = ta.id
         LEFT JOIN customers tc ON ta.customer_id = tc.id
```

And such variants of the filters:
```sql
WHERE transaction_date::DATE = CURRENT_DATE - 10 AND first_name LIKE 'J%';
```
```sql
WHERE email LIKE 'john.smith%';
```
```sql
WHERE transaction_date::DATE = CURRENT_DATE AND c.first_name like 'J%' AND c.email LIKE 'j%';
```

### Any ideas what can we do to not duplicate main part of the query?