## TASK 4
What would happen if we run such query?
```sql
INSERT INTO customer_transactions_view(first_name, last_name, email, account_type, transaction_type, amount)
VALUES ('Petro', 'Stolak', 'p.stolak@gmail.com', 'checking', 'deposit', 100.00);
```
What would happen if we run with `MATERIALIZED VIEW`?