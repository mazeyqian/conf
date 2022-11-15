# config

The configuration files of Nginx and Supervisor.

## Nginx in Guangzhou lighthouse

Edit in the default config: `include /web/feperf.com.conf.d/config/nginxnode/*.conf;`.

Update Nginx server.

```
cd /web/feperf.com.conf.d && git pull && service nginx restart
```

## Nginx in Guangzhou cvm

Update Nginx server.

## Nginx in Tokyo

Edit in the default config: `include /web/feperf.com.conf.d/config/nginxgee/*.conf;`.

Update Nginx server.

```
cd /web/feperf.com.conf.d && git pull && systemctl restart nginx
```

## Supervisor in Mac B

Edit in the `/usr/local/etc/supervisord.conf`: `files = /Users/mazey/Web/Mazey/feperf.com.conf.d/config/supervisorb/*.ini`.

```
brew services restart supervisor
```

## Reference

- http://nginx.org/en/docs/http/server_names.html
