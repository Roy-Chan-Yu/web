## Hashing (雜湊)

- Hashing technique is used to `calculate` the direct `location of a data record on the disk without using index structure`.

## 1. static Hashing

1. Operations of Static Hashing
   
1.  Searching a record
   - the same hash function retrieves the address of the bucket where the data is stored.
2. Insert a Record
   - generate an address for a new record `based on the hash key` and `record is stored in that location.`

## 2. Dynamic Hashing

- The dynamic hashing method is used to `overcome` the problems of `static hashing like bucket overflow`.
  
1. How to insert a new record?
>1. Firstly, `follow the same procedure for     retrieval, ending up in some bucket`.
>2. If there is still space in that bucket, then `place the record in it`.
>3. If the bucket is full, then we will `split the bucket and redistribute[重新調配] the records.`

