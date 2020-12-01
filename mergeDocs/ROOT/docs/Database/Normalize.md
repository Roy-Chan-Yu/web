## Normalization

1. `organizing the data` in the database.
2. It is also used to `eliminate the undesirable characteristics `like Insertion, Update and Deletion Anomalies.
3. Normalization divides the larger table into the smaller table and `links them in the relationship.`
4. `Reduce redundency` from the Table

## Types of Normal Forms

|Normal Form|Description|
|-----------|--------------|
|1NF|A relation is in 1NF if it contains `an atomic value`.|
|2NF|A relation will be in 2NF if it is in 1NF and all `non-key attributes are fully functional dependent on the PK`.|
|3NF|A relation will be in 3NF if it is in 2NF and `no transition dependency exists`.|
|4NF|A relation will be in 4NF if it is in Boyce Codd normal form and has no multi-valued dependency.|
|5NF|A relation is in 5NF if it is in 4NF and not contains any join dependency and joining should be lossless.|

## 1NF

- reduce the duplicate value
  
EMP_ID | EMP_NAME | EMP_PHONE
---------|----------|---------
 14 | John | 7272826385<br>9064738238
 A2 | B2 | C2
 A3 | B3 | 7390372389<br>8589830302
