## TASK 2
What can we do 
```sql
select count(*) from customer_transactions_view where transaction_type = 'transfer' and transaction_date::date = CURRENT_DATE;
```
How can we get a comprehension of what is wrong with execution time?