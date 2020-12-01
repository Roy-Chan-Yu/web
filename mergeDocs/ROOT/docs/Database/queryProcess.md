## Query Processing

- extracting data from the database

1. Parsing and translation
2. Optimization
3. Evaluation


## STEPs in Query Processing
```mermaid 
graph TD;
id[query]
id2{parser and translator}
id3[relation-algebra expression]
id4{optimizer-初步處理}
id5[execution-plan-最佳計畫]
database[(statistics about data)]
id7{evalution engine}
subgraph data
    data1[(data1)]
    data2[(data2)]
end
id8[query output]

id-->id2-->id3-->id4-->id5-->id7-->id8
id7-->data1
id7-->data2
database-->id4
```


## Optimization
- The cost of the query evaluation can `vary for different types of queries.` 
- the query `optimizer should have an estimated cost analysis of each operation`. It is because the overall operation `cost depends on the memory allocations` to several operations, `execution costs`, and so on.

## Evaluation

- In order to fully evaluate a query, the system `needs to construct a query evaluation plan` which is also referred to as the `query execution plan`.