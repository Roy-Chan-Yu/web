## NGINX Tutorial

- NGINX is an `open source, lightweight`, `high-performance` web server
- is considered as the popular web server behind Apache web server and Microsoft's IIS.
- improves `content and application delivery`, improves security, and facilitates scalability[可擴充性] and availability for the busiest website

## Features of NGINX

1. Reverse proxy with caching.
2. IPV6.
3. Load Balancing.
4. Web Socket.
5. Handling of static files,index files.
6. FastCGI support with caching .
7. URL rewriting and redirection.

## Forward Proxy (call a Proxy)

1. it usually let clients on an otherwise
firewall-restricted network to access the internet.
2. improve `the access speed` and `hide the original client's IP address` from any connection target.

> With a forward proxy you send a connection request through it, and it retrieves data from the internet `hiding the client IP`.

## Reverse Proxy

1. provide `anonymity for the back-end servers`, not the clients.
2. above the top, they `mask the real location of the server client are accessing`.
3. it can serve as the `front-facing` part of your service. `It keeps out malicious attacks`.可作為application layer的firewall、提供加密和SSL加速(SSL end-point proxy)、提供HTTP 訪問的認證

4. Reverse proxies can also `boost speed by storing a cached site at the front-end`of the service.

5. Reverse proxies are excellent at balancing server loads and serving cached site version

> A reverse proxy can perform `authentication tasks`, as well as cache or decrypt data. In essence, a reverse proxy `is a gateway to a server` or group of servers.<br> `AS intermediaries`(中介人),

## Forward vs reverse Proxies

> they are `in opposite sides of the connection`<br>
> a Forward Proxy is the intermediary that <font color = "red">the client </font> `put forward between itseltf and any server`.<br>
> The reverse proxy is at the other end – something <font color = "red">the server</font> `puts forward between itself and any client`.
> It only concerns the position viewpoint of the proxy in the client-service connection.  

## Application Delivery

> refers to the pool of services that combine to provide application functionality, usually `web-based software applications`.<br>
> The services on a network infrastructure[基礎設施] aim to provide a reliable user experience just like `load balancing`, `latency and TCP optimization` which combine to provide application content seamlessly.

## Latency and TCP optimization

> Latency is a measure of delay,measured in milliseconds(ms)<br>
> `the round trip delay` - the time taken for information to get to its DEST and BACK again.
> The `round trip delay` is an important measure becautse a node that uses a TCP/IP network sends `a limited amount of data` to its destination and waits for an ACK to come back before sending any more. <br>
> Thus,the round trip delay `has a key impact` on the performance of the network.

## Concurrency

- in growing and demanding more things at one time, `the concurrency` comes into the world and `nginx launched for the same thing.`

## THE C10K Problem

> the challenge of managing 10000 connections at the same time have to handle.
