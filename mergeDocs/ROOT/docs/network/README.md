## Computer network architecture

- defined as the `physical and logical design of the software, hardware, protocols`, and media of `the transmission of data`.
- simply,how computers are organized and how tasks are allocated to the computer.

## Two types of network

- Peer-to-Peer network
- Client/Server network

```mermaid
graph TD;
id[Types Of Computer Network]
id2[Peer-to-Peer network]
id3[Client/Server network]
id-->id2
id-->id3
style id fill:#f9f,stroke:#333,stroke-width:4px,color:#fff
style id2 fill:#bbf,stroke:#f66,stroke-width:2px,color:#fff
style id3 fill:#b5b,color:#fff
```

## Peer-To-Peer network

- is a network in which all the computers `are linked together with equal privilege and responsibilities` for processing the data.
- Peer-To-Peer network is `useful for small environments`, usually up to 10 computers.
- Peer-To-Peer network has `no dedicated server`.
- `Special permissions are assigned to each computer` for sharing the resources, but this can lead to `a problem if the computer with the resource is down`.

```mermaid
graph TD;
id(node1)
id2(node2)
id3(node3)
id4(node4)
id5(node5)
id6(node6)
id7(node7)
id8(node8)
id---id2;id---id3;id---id8;id3---id4;id2---id4;id4---id5;id4---id6;id5---id6;id4---id7;id8---id4;
```

## Advan. of Peer-to-Peer Network

1. It is less `costly as it does not contain any dedicated server`.
2. If one computer stops working but, other computers will not stop working.
3. It is `easy to set up and maintain as each computer manages` itself.

## disAdvan

1. it does `not contain the centralized system`. Therefore, it `cannot back up the data as the data is different in different locations`(異地備援)
2. It has a `security issue` as the device is managed itself.

## Client/Server network

- Client/Server network is a network model designed for the `end users called clients`, to `access the resources from a central computer` known as Server.

to-do

```mermaid
graph TD;
id(fa:fa-mobile)
id2(fa:fa-laptop)
id3(fa:fa-desktop)
id4{fa:fa-cloud-upload Internet}
id5[(fa:fa-server Server)]
id-->id4
id2-->id4
id3-->id4
id4-->id5
```

## Advantages Of Client/Server network

1. contains the `centralized system`. Therefore we can back up the data easily.
2. has a `dedicated server that improves the overall performance` of the whole system.
3. better in Client/Server network as a single server administers the shared resources.
4. `increases the speed` of the sharing resources.

## disAdv

1. requires a dedicated network administrator to manage all the resources.
2. `Client/Server network is expensive` as it requires the server `with large memory`.
