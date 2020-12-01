## Index

> `optimize the performance` of a database by `minimizing the number of disk accesses` required when a query is processed


Index | Structure |
---------|------|
 Search-key |  Data-reference

## 1. Indexing Method

```mermaid
graph TD;
id[Indexng methods]
subgraph method1
    id2[Ordered indices]
    id3[Primary Index]
    id4[Clustering Index]
    id5[Secondary Index]
end
subgraph method2
    id6[Dense Index]
    id7[Sparse Index]
end
    style id fill:#f9f,stroke:#333,stroke-width:4px
    style method1 fill:#bbf,stroke:#f66
id-->id2
id-->id3
id-->id4
id-->id5
id3-->id6
id3-->id7    
```

## 2. B+ Tree 

> Big-O (O) ->即最糟情況下的執行次數(COST)

- `balanced binary search tree`. It follows a `multi-level index` format
  
-  leaf nodes denote actual data pointers. B+ tree ensures that `all leaf nodes remain at the same height`.

- using a `link list`. Therefore, a B+ tree can support random access as well as `sequential access`.