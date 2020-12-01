## Nginx security control

- We are rightly concerned about the privacy and security of our users.

## NGINX SSL Termination

1. SSL (Secure Socke Layer) connection uses a certificate for authentication before `sending encrypted data from a client computer to the webserver.`
2. `SSL termination is a form of SSL offloading[分流](decryption)`, shift some of responsibility from the webserver to a different machine.`SSL termination is used to recongnize encrypted data`.

## How to configure as HTTPS server on NGINX

### set up an https server in out nginx.conf

```conf
server {  
    listen              443 ssl;  
    server_name         www.example.com;  
    ssl_certificate     www.example.com.crt;  
    ssl_certificate_key www.example.com.key;  
    ssl_protocols       TLSv1 TLSv1.1 TLSv1.2;  
    ssl_ciphers         HIGH:!aNULL:!MD5;  
    #...  
}  
```

## SSL Termination for TCP Upstream Servers

### ssl_certificate

```conf
server {  
    #...  
    ssl_certificate        /etc/ssl/certs/server.crt;  
    ssl_certificate_key    /etc/ssl/certs/server.key;  
}  
```

## ssl_protocols and ssl_ciphers directives can be used to limit connections

```conf
    #...  
  ssl_protocols  TLSv1 TLSv1.1 TLSv1.2;  
  ssl_ciphers    HIGH:!aNULL:!MD5;
```
