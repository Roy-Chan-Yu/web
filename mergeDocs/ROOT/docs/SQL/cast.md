## SQL CAST Function

- We use the CAST function to convert `numeric data into character or string data`.

```sql
SELECT First_Name, CAST (Score AS Integer)  
Int_Score FROM Student_Score;  
```

```sql
SELECT First_Name, CAST (Score AS char (3))  
Char_Score FROM Student_Score;  
```
