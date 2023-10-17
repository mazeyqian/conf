# config

The configuration files of Nginx and Supervisor.

- [config](#config)
  - [Default](#default)
    - [Nginx Configuration](#nginx-configuration)
    - [Supervisor Configuration](#supervisor-configuration)
  - [Servers](#servers)
    - [Nginx in Guangzhou lighthouse](#nginx-in-guangzhou-lighthouse)
    - [Nginx in Guangzhou cvm](#nginx-in-guangzhou-cvm)
    - [Nginx in Tokyo](#nginx-in-tokyo)
    - [Nginx in Mac B](#nginx-in-mac-b)
    - [Supervisor in Guangzhou lighthouse](#supervisor-in-guangzhou-lighthouse)
    - [Supervisor in Japan Vultr](#supervisor-in-japan-vultr)
    - [Supervisor in Mac B](#supervisor-in-mac-b)
  - [Reference](#reference)

## Default

### Nginx Configuration

Linux:

```shell
vim /etc/nginx/nginx.conf
```

Mac:

```shell
vim /usr/local/etc/nginx/nginx.conf
```

### Supervisor Configuration

Linux:

```shell
vim /etc/supervisord.conf
```

Mac:

```shell
vim /usr/local/etc/supervisord.conf
```

Modify the file:

```text
[include]
files = /your/path1/*.ini
files = /your/path2/*.ini
```

## Servers

### Nginx in Guangzhou lighthouse

Edit in the default config: `include /web/conf/config/nginxnode/*.conf;`.

Update Nginx server.

```shell
cd /web/conf && git pull && service nginx restart
```

### Nginx in Guangzhou cvm

Edit in the default config: `include /web/conf/config/nginxmazey/*.conf;`.

Update Nginx server.

```shell
cd /web/conf && git pull && service nginx restart
```

### Nginx in Tokyo

Edit in the default config: `include /web/conf/config/nginxgee/*.conf;`.

Update Nginx server.

```shell
cd /web/conf && git pull && systemctl restart nginx
```

### Nginx in Mac B

```shell
# Start
/usr/local/bin/nginx

# Reload
nginx -s reload
```

### Supervisor in Guangzhou lighthouse

Edit in the `/etc/supervisord.conf`: `files = /web/conf/config/supervisornode/*.ini`.

```shell
# Init First
systemctl start supervisord
systemctl status supervisord
systemctl enable supervisord

# Restart
systemctl restart supervisord
```

### Supervisor in Japan Vultr

Edit in the `/etc/supervisord.conf`: `files = /web/conf/config/supervisorjapan/*.ini`.

```shell
vim /etc/supervisord.conf

/web/conf/config/supervisorjapan/*.ini
```

### Supervisor in Mac B

Edit in the `/usr/local/etc/supervisord.conf`: `files = /your/path/conf/config/supervisorb/*.ini`.

```shell
brew services restart supervisor
```

Reload the Supervisor configuration:

```shell
supervisorctl reread
```

Start the program:

```shell
supervisorctl start app_name
```

Stop the program:

```shell
supervisorctl stop app_name
```

Restart the program:

```shell
supervisorctl restart app_name
```

Check the status:

```shell
supervisorctl status
```

## Reference

- [Server names](http://nginx.org/en/docs/http/server_names.html)
