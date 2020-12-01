## HTTP Load Balancing

- load balance HTTP traffic to a group of servers, first, we need to define the group with the upstream directive. The `directive is placed in the http context`.

## default.conf

- the following configuration defines a group named backend and consists of three server configurations that may resolve in more than three actual servers.

```conf
http {  
    upstream backend {  
        server backend1.example.com weight=5;  
        server backend2.example.com;  
        server 192.0.0.1 backup;  
    }  
}  
```

## Pass requests to a server group, the group name is specified in the proxy_pass directive

- a virtual server run on Nginx pass all requests to the upstream backend group.

```conf
server {
    location /{
        proxy_pass http: //upstream -> backend;
    }
}
```
