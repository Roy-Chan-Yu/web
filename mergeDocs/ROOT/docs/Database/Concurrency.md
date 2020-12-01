## Concurrency Control

## 1.Problems of concurrency control

- Lost updates
- Dirty Read
- Unrepeatable Read

1. Lost-Update

> If two transactions `T1 and T2 read a record and then update it`, then the effect of updating of the first record will `be overwritten by the second update`.

2. Dirty-Read

> A transaction T1 update a record which is read by T2 and `T1 aborts`,then the value which is not `persist of the stable data`.

3. InConsistent Retrieval Problem

- like top

## 2. Recovery with Concurrent Transaction

> To ease this situation, `CheckPoint` concept is used by most DBMS.