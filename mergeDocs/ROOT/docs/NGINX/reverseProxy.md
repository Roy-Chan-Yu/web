## ReversingProxy

- Proxy_pass

```conf
location /some/path/ {  
    proxy_pass http://www.example.com/link/;  
}  
```

## To pass a request to a non-HTTP proxied server, use the appropriate **_pass directive

- fastcgi_pass: it passes a request to a fastCGI server.
- uwsgi_pass: it passes a request to an uwsgi server.

- scgi_pass: it passes a request to an SCGI server.

- memcached_pass: it passes a request to a memcached server.
