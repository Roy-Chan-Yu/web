## SQL Introduce

- With SQL, we can query our database in several ways, using English-like statements.
- With SQL, a user can access data from a relational database management system.
- It allows the user to describe the data.
- It allows the user to define the data in the database and manipulate it when needed.
- It allows the user to create and drop database and table.
- It allows the user to create a view, stored procedure, function in a database.
- It allows the user to `set permission on tables, procedures, and views`.

## Difference Between Delete,Truncate and Drop 


Definition | Delete | Truncate | Drop
------|---------|----------|---------
Free the space |N | Y | Y

## When Drop the table valid whereas it's not to truncate

> - Table structure will be dropped
> - Relationship will be dropped
> - Integrity constraints will be dropped
> - Access privileges will also be dropped

## SQL TEMP TABLE

- Temporary tables can be created at `run-time` and can do all kinds of operations that a normal table can do. 

#### MSSQL  

```sql
CREATE TABLE #local temp table (  
User id int,  
Username varchar (50),  
User address varchar (150)  
)  
```

## ALTER TABLE

- The ALTER TABLE statement is used to `add, modify or delete columns` in an `existing table`. It is also used to rename a table.

### SQL ALTER TABLE Add Column
```sql
ALTER TABLE table_name ADD column_name column-definition
```

### SQL ALTER TABLE Modify Column

```sql
ALTER TABLE table_name MODIFY column_name column_type;  
```

### SQL ALTER TABLE DROP Column

```sql
ALTER TABLE table_name DROP COLUMN column_name;
```

SQL ALTER TABLE RENAME Column

```sql
ALTER TABLE table_name  
RENAME COLUMN old_name to new_name;  
```