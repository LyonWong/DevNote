# Linux

## vim
```
set ts=4
set ss=4
set sw=4
set nu
set autoindent
set smartindent
```

## nginx
```
server {
    listen 80;
    server_name www.domain.com;
    root /var/www;
    location \.php$ {
        fastcgi_pass unix:/run/php/php-fpm.sock;
        #fastcgi_pass 127.0.0.1:9000;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
```