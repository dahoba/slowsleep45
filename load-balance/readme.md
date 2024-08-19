# Load balance

## nginx

/etc/nginx/conf.d$/example.conf:

```
upstream backend {
    server 192.168.1.122:2001;
    server 192.168.1.122:2002;
    server 192.168.1.122:2003;
}

server {
  listen  80;
  listen  [::]:80;
  server_name whoami.example;
  root /usr/share/nginx/example.com;

  location / {
    proxy_pass http://backend;
  }
}
```

## Backend

starting port 2001,2002,2003

```
docker compose -f compose.yml up -d
```