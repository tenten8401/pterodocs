---
title: 'Nginx Requirements'
taxonomy:
    category: docs
---

Pterodactyl Panel is designed to run on your own web server. You will need to have root access to your server in order to run and use this panel.

**Supported Environments**
* Ubuntu Server 14.04 LTS (Trusty Tahr) & 16.04 LTS (Xenial Xerus)
* CentOS 7
* Debian 8 requires kernel modifications for daemon

!! Using Ubuntu Server 14.04 LTS (Trusty Tahr) might cause some issues as it does not provide the latest versions of some packages, using Ubuntu Server 16.04 LTS (Xenial Xerus) is recommended.

**Dependencies**
* PHP >= ```7.0.0``` (PHP 7.1 recommended) with the following extensions:
 	* CLI ```php7.1-cli``` 
 	* OpenSSL (included with packaged versions)
 	* GD ```php7.1-gd``` 
 	* MySQL ```php7.1-mysql```
 	* PDO ```php7.1-pdo```
 	* MBString ```php7.1-mbstring```
 	* Tokenizer ```php7.1-tokenizer```
 	* BCMath ```php7.1-bcmath```
 	* DOM ```php7.1-xml or php7.1-dom```
 	* cURL ```php7.1-curl```
 	* Zip ```php7.1-zip```
 
* MySQL ```>= 5.7``` or MariaDB ```>= 10.1```
* Nginx or Apache
	* If using NGINX ensure you install ```php7.1-fpm```
* cURL ```curl```
* Tar ```tar```
* Unzip ```unzip```
* Memcached ```memcached``` & ```php7.1-memcache``` or Redis ```redis```
* Git ```git```

**Install Dependencies**
These commands should work on most modern Ubuntu distributions.
```
# Add additional PHP packages.
add-apt-repository -y ppa:ondrej/php
curl -sS https://downloads.mariadb.com/MariaDB/mariadb_repo_setup | sudo bash

# Update repositories list
apt update

# Install Dependencies
apt-get -y install php7.1 php7.1-cli php7.1-gd php7.1-mysql php7.1-pdo php7.1-mbstring php7.1-tokenizer php7.1-bcmath php7.1-xml php7.1-fpm php7.1-memcached php7.1-curl php7.1-zip mariadb-server nginx curl tar unzip git memcached
```