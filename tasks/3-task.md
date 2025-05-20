## TASK 3
### Part 1
If we create such a view, will it help somehow?
```sql
CREATE VIEW customer_transactions_view AS
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
```sql
SELECT * FROM customer_transactions_view;
```

### Part 2
If we create such a materialized view, will it help somehow?
```sql
CREATE MATERIALIZED VIEW customer_transactions_materialized_view AS
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
```sql
SELECT * FROM customer_transactions_materialized_view;
```