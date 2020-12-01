## Manipulation NGINX

- commands to start, stop, restart or reload the Nginx.

## LINUX distribution(發行版)

- 從linux kernel 衍生出來的 i.e.`Ubuntu`,`CentOS`,`Debian`,Red Hat Enterprise Linux,Fedora,

## Start Nginx

```bash
sudo systemctl start nginx  
```

### Linux distribution

```bash
sudo service start nginx
```

### Older Ubuntu Linux version

```bash
sudo /etc/init.d/nginx start
```

## Enable Nginx service

- recommended to enable it auto-start at boot time OR REBOOT

```bash
sudo systemctl enable nginx
```

### Linux distribution

```bash
sudo service nginx enable
```

## STOP Nginx

```bash
sudo systemctl stop nginx
```

### Linux Distribution

```bash
sudo service stop nginx
```

### Older Ubuntu version

```bash
sudo /etc/init.d/nginx stop
```

### compiled and installed from the source code

```bash
sudo /etc/init.d/nginx stop
```

## Restart Nginx

```bash
sudo systemctl restart nginx
```

### Linux Distribution

```bash
sudo service restart nginx
```

### Older Ubuntu linux version

```bash
sudo /etc/init.d/nginx/restart
```

## Reload Nginx

- We need to restart or reload Nginx where  we make change to its configuration.
- The reload option load the new config,shut down old worker processes.

```bash
sudo systemctl reload nginx
```

### Linux distribution

```bash
sudo service reload nginx
```
