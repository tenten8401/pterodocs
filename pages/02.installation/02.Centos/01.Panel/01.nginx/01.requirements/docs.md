---
title: Requirements
taxonomy:
    category:
        - docs
---

#### Installing REMI repo

```
yum install -y epel-release https://rpms.remirepo.net/enterprise/remi-release-7.rpm
sed -i -e 's/enabled=0/enabled=1/1' /etc/yum.repos.d/remi.repo
sed -i -e 's/enabled=1/enabled=0/1' /etc/yum.repos.d/remi-safe.repo
```

#### Installing nginx, php 7.1, and memcached

```
yum update -y
yum install -y nginx php71-php php71-php-common php71-php-fpm php71-php-cli php71-php-json php71-php-mysqlnd php71-php-mcrypt php71-php-gd php71-php-mbstring php71-php-pdo php71-php-zip php71-php-bcmath php71-php-dom php71-php-pear php71-php-opcache php71-php-pecl-memcached memcached
ln -s /usr/bin/php71 /usr/bin/php
ln -s /usr/bin/php71-phar /usr/bin/php-phar
ln -s /usr/bin/php71-cgi /usr/bin/php-cgi
```

#### Install Composer
```
curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
```

!! This does not install or configure MySQL/MariaDB on your server. You are expected to install those, and configure, on your own.  
!! We have a tutorial that you can follow in the [Tutorials](/tutorials) section.