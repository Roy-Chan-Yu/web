## Apache VS NGINX

| Apache| NGINX|
|----------------------------------------- | --------------- |
| Apache runs on all Unix like systems such `as Linux, BSD, etc. as well as completely supports Windows.` | Nginx runs on modern Unix like systems; has limited support for Windows.|
| Apache uses a multi-threaded approach to process client requests.| Nginx follows an `event-driven approach to serve client requests.`|
| Apache cannot handle multiple requests concurrently with heavy web traffic.| Nginx can handle multiple client `requests concurrently and efficiently with limited hardware resources`.|
| Apache `processes dynamic content within the web server` itself.| NGINX can't process dynamic contentnatively.|
| Apache is designed to be a web server.| Nginx is both a `web server and a proxy server.`|
| Modules are dynamically `loaded or unloaded`, making it more flexible.| Since modules cannot be loaded dynamically, they must be compiled within the core software itself.|
| A single thread can only process one connection.| A single thread can `handle multiple connections`.|
| The performance of Apache for static content is lower than Nginx.| Nginx can `simultaneously run thousands of connections`of static content two times `faster than Apache and uses little less memory`.|
