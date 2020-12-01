## Primary Key

- primary key (PK) that `uniquely identifies each row` in the table.

## Multiple columns are used as a primary key

> `it's known as composite privary key`

## Design the composite primary key

> 1. use as a fewer columns as possible.
>
> - it's good for storage and performance both.

## Points to remember for primary key

1. Primary key enforces the entity integrity of the table.
2. primary key length cannot be exceeded than 900 bytes.
3. A table can contain `only one primary key constraint`

> ADD CONSTRAINT pk_name PRIMARY KEY(P1,P2,P3)<br><br>
> Have a PK(in Logical) with P1,P2,P3...combination<br><br>
>When we specify a primary key constraint for a table, database engine automatically creates a `unique index for the primary key column`.

## CREATE CONSTRAINT IN CREATING TABLE

```sql
CREATE TABLE YU2(
S_ID int,
LastName varchar(25),
City varchar(20),
CONSTRAINT YU2_PK PRIMARY KEY(S_ID,LastName)
)
```

> Note:you should note that in the above example there is only one PRIMARY KEY (pk_StudentID). However it is `made up of two columns` (S_Id and LastName).

## FOREIGN KEY

- A foreign key in one table used to `point primary key in another table`.

| S_Id | LastName | FirstName | CITY      |
| ---- | -------- | --------- | --------- |
| 1    | MAURYA   | AJEET     | ALLAHABAD |
| 2    | JAISWAL  | RATAN     | GHAZIABAD |
| 3    | ARORA    | SAUMYA    | MODINAGAR |

---

| O_ID | OrderNO | S_ID |
| ---- | ------- | ---- |
| 2    | 995864  | 2    |
| 2    | 995865  | 2    |
| 3    | 995866  | 3    |
| 4    | 995867  | 1    |

> The foreign key constraint is generally prevents action that destroy links between table.<br><br>
> ORA-02292: integrity constraint (VAPCADM.YU2_FK) violated - child record found.

## difference between primary key and foreign key in SQL

| Diff            | Primary | Foreign                    |
| --------------- | ------- | -------------------------- |
| isNull          | N       | Y                          |
| isUnique        | Y       | N(duplicated key)          |
| only-one Key    | Y       | N                          |
| autoCreateIndex | Y       | N(you must manually create |

## COMPOSITE KEY 複合主鍵

- Composite key is a key which is the combination of more than one field or column of a given table. It may be a `candidate key` or `primary key`.

Oracle

```
CREATE TABLE SAMPLE_TABLE  
CREATE TABLE SAMPLE_TABLE  
(COL1 integer,  
COL2 varchar(30),  
COL3 varchar(50),  
PRIMARY KEY (COL1, COL2));  
```

## Unique Key

- You can say that it is little `like primary key` but it can accept `only one null value` and it cannot have duplicate values.
  
```sql
 CREATE TABLE students  
(  
S_Id int NOT NULL,  
LastName varchar (255) NOT NULL,  
FirstName varchar (255),  
City varchar (255),  
CONSTRAINT uc_studentId UNIQUE (S_Id, LastName)  
)  
```

## Alternate Key

- if a table has more than a candidate key ,
  one of them will become the primary key
  and `rest of all are` called alternate keys...

> An alternate key is just a candidate key that `has not been selected as the primary key`.
