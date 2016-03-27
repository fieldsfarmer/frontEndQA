##### inner join
##### count 
```sql
select City from
(
	select City, count(*)  as Times
	from Customers
	group by City
)
where Times > 1;
```