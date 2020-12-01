## SQL CONCAT Function

- The CONCAT function in SQL is a String function, which is used to merge two or more strings.

```sql
SELECT CONCAT ('FIRST', 'SECOND') from dual
```

## NULL CONCAT

> Concat service converts `the Null values to an Empty string` when we display the result

```sql
SELECT CONCAT (null, 'SECOND') from dual -- SECOND
select null || 'SECOND' FROM dual
```
