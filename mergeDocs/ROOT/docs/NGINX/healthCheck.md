## HTTP Healthy Checks

- Avoid the servers that have failed,
and `gracefully add the recovered servers into the load-balanced group`

## ICON health_check

URI (Uniform Resource Identifier)

```conf
location / {
    proxy_pass http://backend;
    health_check uri = /some/path;
}
```
