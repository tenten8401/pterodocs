---
title: Panel
---

Pterodactyl Panel is designed to run on your own web server. You will need to have root access to your server in order to run and use this panel.

## Dependencies
* PHP ```>= 7.0.0``` (PHP 7.1 recommended) with the following extensions:
    * CLI `php7.1-cli`
    * OpenSSL (included with packaged versions)
    * GD `php7.1-gd`
    * MySQL `php7.1-mysql`
    * PDO `php7.1-pdo`
    * MBString `php7.1-mbstring`
    * Tokenizer `php7.1-tokenizer`
    * BCMath `php7.1-bcmath`
    * DOM `php7.1-xml` or `php7.1-dom`
    * cURL `php7.1-curl`
    * Zip `php7.1-zip`
* MySQL `>= 5.7` or [MariaDB](https://downloads.mariadb.org/mariadb/repositories/#mirror=jaleco) `>= 10.1`
* Nginx, Apache, or Caddy
* cURL `curl`
* Tar `tar`
* Unzip `unzip`
* Memcached `memcached` & `php7.1-memcache` **or** Redis `redis`
* Git `git`