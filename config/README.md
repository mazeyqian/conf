# config

The configuration files of Nginx and Supervisor.

- [config](#config)
  - [Nginx Configuration](#nginx-configuration)
  - [Supervisor Configuration](#supervisor-configuration)
  - [Nginx in Guangzhou lighthouse](#nginx-in-guangzhou-lighthouse)
  - [Nginx in Guangzhou cvm](#nginx-in-guangzhou-cvm)
  - [Nginx in Tokyo](#nginx-in-tokyo)
  - [Nginx in Mac B](#nginx-in-mac-b)
  - [Supervisor in Mac B](#supervisor-in-mac-b)
  - [Supervisor in Guangzhou lighthouse](#supervisor-in-guangzhou-lighthouse)
  - [Supervisor in Japan Vultr](#supervisor-in-japan-vultr)
  - [Reference](#reference)

## Nginx Configuration

Linux:

```
vim /etc/nginx/nginx.conf
```

Mac:

```
vim /usr/local/etc/nginx/nginx.conf
```

## Supervisor Configuration

Linux:

```
vim /etc/supervisord.conf
```

Mac:

```
vim /usr/local/etc/supervisord.conf
```

## Nginx in Guangzhou lighthouse

Edit in the default config: `include /web/conf/config/nginxnode/*.conf;`.

Update Nginx server.

```
cd /web/conf && git pull && service nginx restart
```

## Nginx in Guangzhou cvm

Update Nginx server.

## Nginx in Tokyo

Edit in the default config: `include /web/conf/config/nginxgee/*.conf;`.

Update Nginx server.

```
cd /web/conf && git pull && systemctl restart nginx
```

## Nginx in Mac B

```
nginx -s reload
```

## Supervisor in Mac B

Edit in the `/usr/local/etc/supervisord.conf`: `files = /Users/mazey/Web/Mazey/conf/config/supervisorb/*.ini`.

```
brew services restart supervisor
```

## Supervisor in Guangzhou lighthouse

Edit in the `/etc/supervisord.conf`: `files = /web/conf/config/supervisornode/*.ini`.

```
# Init First
systemctl start supervisord
systemctl status supervisord
systemctl enable supervisord

# Restart
systemctl restart supervisord
```

## Supervisor in Japan Vultr

Edit in the `/etc/supervisord.conf`: `files = /web/conf/config/supervisorjapan/*.ini`.

```
vim /etc/supervisord.conf

/web/conf/config/supervisorjapan/*.ini
```

## Reference

- [Server names](http://nginx.org/en/docs/http/server_names.html)
