## SQL add/drop/update column operation

- ALTER TABLE is mainly used to delete, add, or modify the columns into an existing table. It is also used to add many constraints on the current table.

## Add column

```sql
ALTER TABLE "table_name"  
ADD "column_name" "Data Type";  
```

## Add multiple columns to the table

```sql
ALTER TABLE Student ADD (Telephone char(15), Email char(20) );
```

## Drop table

```sql
ALTER TABLE table_name
DROP COLUMN column_name;  
```

## Alter table Modify

- Multiple columns can be changed at once.

```sql
ALTER TABLE table_name  
MODIFY column_name column_type;  
```
