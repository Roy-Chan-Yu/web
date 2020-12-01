## SELECT Multiple

## WITH

> The SQL WITH clause is used to provide a sub-query block which can be referenced in several places within the main SQL query

```sql
WITH A AS (
SELECT spg.GRP_NAME,spg.GRP_ID FROM SYS_PARA_GRP spg
)SELECT A.GRP_NAME,A.GRP_ID,spn.PARA_NAME FROM A,SYS_PARA_NAME spn
 WHERE A.GRP_ID = spn.GRP_ID
 AND spn.LAISO = 'ZF';
```

## LIMIT

Oracle

- If you want to use LIMIT clause with SQL, you have to use `ROWNUM` queries because it is used `after result are selected`.

### This query give 3rd to 5th rows

```sql
SELECT * FROM (SELECT SHORT_DESC ,ROWNUM r FROM (
SELECT mvg.GENDER_ID ,mvg.SHORT_DESC FROM MAT_VT_GENDER mvg
WHERE ROWNUM <= 5
ORDER BY mvg.GENDER_ID
 )
)
WHERE r>2;
```

## INSERT MULTIPLE ROWS

- Many times developers ask that is it possible to `insert multiple rows` into a single table in a `single statement`

```sql
INSERT INTO YU(COL1,COL2)
SELECT '1','2' FROM dual
UNION ALL
SELECT '3','4' FROM dual
UNION ALL
SELECT '5','6' FROM dual;
```

## Updating Multiple Fields

### EXISTS

```sql
UPDATE YU y2 SET COL2 = 10
WHERE EXISTS (
SELECT 'Y'
FROM YU y
WHERE y2.YOURDATE > TO_DATE('20201030 11:00:00','yyyyMMdd HH24:MI:SS')
AND y2.COL1 = y.COL1 );
```

## UPDATE DATE

```sql
UPDATE YU SET
YOURDATE = '20201101 12:20:25'
WHERE COL1 = 1
```

## DROP INDEX

### DROP Oracle

```sql
DROP INDEX index_name
```

### DROP MSSQL

```sql
DROP INDEX table_name.index_name
```

## DROP VIEW

```sql
DROP VIEW view_name
```

## GROUP

- The Group By statement is used for organizing similar data into groups

### GROUP By single

- Group By single column `is used to place all the rows with the same value in one group.`
  
-- full table

| ID                     | SUBJECT    | DAYSOFYEAR | NAME    | SALARY |
| ---------------------- | ---------- | ---------- | ------- | ------ |
| st9R-8Dj8U3gUBCscQFz6g | C language | 2          | John    | 25000  |
| st9R-8Dk8U3gUBCscQFz6g | C language | 2          | Ginny   | 28000  |
| st9R-8Dl8U3gUBCscQFz6g | C language | 2          | Jasmeen | 26000  |
| st9R-8Dm8U3gUBCscQFz6g | C language | 3          | Nick    | 27000  |
| st9R-8Dr8U3gUBCscQFz6g | C language | 3          | Amara   | 29000  |
| st9R-8DQ8U3gUBCscQFz6g | JAVA       | 1          | Sifa    | 31000  |
| st9R-8Dm8U3gUBCscQFK6g | JAVA       | 1          | Dolly   | 30000  |

```sql
SELECT subject,MAX(salary),count(1) FROM yu_student
GROUP BY subject
```

| Subject    | SALARY | count |
| ---------- | ------ | ----- |
| C language | 29000  | 5     |
| JAVA       | 31000  | 2     |

```sql
SELECT ys.SUBJECT FROM YU_STUDENT ys
GROUP BY ys.SUBJECT
HAVING MAX(SALARY) >= 30000;
```

### GROUP BY Clause 
- Groups rows that share a property so that the aggregate function can be applied to each group.

### Having Clause
- It selects among the group defined by the GROUP BY CLAUSE.

> Having Clause Bind to Group Clause

## TOP 
- The top clause specifies that how many rows are returned.

```sql
SELECT TOP 2 * FROM employee  
```

## Get Last

MySQL syntax

```sql
SELECT column_name FROM table_name  
ORDER BY column_name DESC  
LIMIT 1;  
```
MSSQL Server

```sql
SELECT TOP 1 column_name FROM table_name  
ORDER BY column_name DESC;  
```

Oracle Server

```sql
SELECT column_name FROM table_name   
ORDER BY column_name DESC
WHERE ROWNUM<=1;
```
