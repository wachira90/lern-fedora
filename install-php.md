# install php

## Import Remi PHP Repository for Fedora 37
````
sudo dnf install http://rpms.remirepo.net/fedora/remi-release-37.rpm -y
````

## Import Remi PHP Repository for Fedora 36
````
sudo dnf install http://rpms.remirepo.net/fedora/remi-release-36.rpm -y
````

## Import Remi PHP Repository for Fedora 35
````
sudo dnf install http://rpms.remirepo.net/fedora/remi-release-35.rpm -y
````


````
dnf repolist | grep remi

dnf module list php
````

## Enable PHP 8.2 on Fedora.
````
sudo dnf module enable php:remi-8.2 -y
````

## Enable PHP 8.1 on Fedora.
````
sudo dnf module enable php:remi-8.1 -y
````

## Enable PHP 8.0 on Fedora.
````
sudo dnf module enable php:remi-8.0 -y
````

## Enable PHP 7.4 on Fedora.
````
sudo dnf module enable php:remi-7.4 -y
````

## Apache (httpd) PHP:
````
sudo dnf install php php-cli -y
````

## Nginx PHP:

````
sudo dnf install php-fpm php-cli -y
````

## most commonly used

````
dnf install php-cli php-fpm php-curl php-mysqlnd php-gd php-opcache php-zip php-intl php-common php-bcmath php-imagick php-xmlrpc php-json php-readline php-memcached php-redis php-mbstring php-apcu php-xml php-dom php-redis php-memcached php-memcache

sudo dnf install php-{cli,fpm,curl,mysqlnd,gd,opcache,zip,intl,common,bcmath,imagick,xmlrpc,json,readline,memcached,redis,mbstring,apcu,xml,dom,redis,memcached,memcache}

php -m
````
## development

````
sudo dnf install php-devel
sudo dnf install php-xdebug php-pcov
````

## Set Up Nginx user for PHP-FPM
nano /etc/php-fpm.d/www.conf

## EDIT
````
user = nginx
group = nginx
````

````
location ~ \.php$ {
    try_files $uri =404;
    fastcgi_pass unix:/run/php-fpm/www.sock;
    fastcgi_index   index.php;
    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
    include fastcgi_params;
}
````

## install qemu-guest-agent

````
yum install qemu-guest-agent -y
````

## restart service

````
systemctl start qemu-guest-agent
````
