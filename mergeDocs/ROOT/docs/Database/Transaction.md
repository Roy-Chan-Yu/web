## Transaction

## 1.The transaction has the four properties.

### 1.1 Atomicity

> means either all successful or none

### 1.2 Consistency

> Ensure the consistent from one consistant to another consistant state.<br>寫入的資料必須完全符合所有的預設
> ATM-deposit


### 1.3 Isolation

> Ensure that transaction is isolated from other transaction.

### 1.4 Durability(耐用性)

> means once a transaction has been commited,it'll remain it ,even in the event of power loss.

## 2.State of Transaction Flow

```mermaid
graph LR;
id[Open_Session]
id2((Active))
id3((Partially-Committed))
id4((Committed))
id5((Failed))
id6((Aborted))
id7[Close_Session]
id-->id2;
id2-->id3-->id4-->id7
id3-->id5
id2-->id5-->id6-->id7
```

### Active state 

> `Insertion or deletion or updating` a record is done here. But all the records are `still not saved to` the database.

## 3.Failure Classification

1. Transaction failure
2. System Crash
3. Disk failure

## 4.Log-based Recovered
- When the system is crashed, then the system `consults the log to find` which transactions need to be undone and `which need to be redone`.
1. Start
><Tn, Start>
2. transaction Modifies
><Tn, City,'Nokia','Bang'>
3. finished
><Tn,Commit>

## 5.CheckPoint-Recovered

- The checkpoint is a type of mechanism which is like to bookmark

```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section CheckPoint
    A task           :a1, 2020-01-01, 1d
    A checkpoint     :2020-01-02
    A durability     :2020-01-02, 1d
    A Failure        :2020-01-03
    A Failure        :after al, 2020-01-03,1d
```


## DeadLock 

- A deadlock is a condition where `two or more transactions are waiting indefinitely for` one `another to give up locks`.