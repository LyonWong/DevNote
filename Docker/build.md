# Build

## Host
```
etc # config
  |-docker
    |-nginx/conf.d => nginx:/etc/nginx/conf.d
data # service data
  |-mysql
  |-redis
usr/local/projects # project files
  |-laravel
  |-wordpress
  |-...
```

## CentOS
## Nginx
- config `/etc/nginx`
## PHP-FPM
- config `/usr/local/etc/fpm`
- docroot `/var/www`
## Mysql
- datadir
## Redis
- data `/data/redis`


