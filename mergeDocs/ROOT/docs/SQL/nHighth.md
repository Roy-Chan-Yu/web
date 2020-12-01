## n-Highth

- In order to calculate the `n-1 highest` salary use `rownum < n`

```sql
select min(salary) from
(select distinct salary from emp order by salary desc)
where rownum < 3
```
