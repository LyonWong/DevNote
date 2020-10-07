# Docker Setup

## download
- [Download](https://www.docker.com)

## images

- `docker pull centos`
- `docker pull mysql`
- `docker pull redis`

## run
```
docker run -it $container /bin/bash
```

## host
- `host.docker.internal`
- `gateway.docker.internal`
- `kubernetes.docker.internal`

## mysql
```
docker run -itd --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=lyonwong mysql
```
- dir
  - basedir `/usr/`
  - datadir `/var/lib/mysql` 

## PHP
### php-fpm
- `docker pull php:v.x-fpm`
- dir
  - fpm-config `/usr/local/etc`
  - www-root `/var/www`
- ext
  - mysql `docker-php-ext-install pdo_mysql`
  - redis 
    - [download](https://github.com/phpredis/phpredis/release)
    - unzip and move to `/usr/src/php/ext/redis`
    - `docker-php-ext-install redis`
