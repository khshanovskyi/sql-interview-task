## TASK 4
We have some `MATERIALIZED VIEW` with the name `customer_transactions_materialized_view`.

What would happen if we run such query?
```sql
INSERT INTO customer_transactions_materialized_view(first_name, last_name, email, account_type, transaction_type, amount)
VALUES ('Petro', 'Stolak', 'p.stolak@gmail.com', 'checking', 'deposit', 100.00);
```
