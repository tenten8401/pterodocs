---
title: Setup
taxonomy:
    category: docs
---

#### Configure pterodactyl.conf
Grab the [nginx ssl config](pterodactyl-conf) in the pterodactyl.conf area under this one.

Paste the nginx config into the `/etc/nginx/conf.d/pterodactyl.conf`

#### Configure php-fpm
Grab the php-fpm [www.conf](php-fpm) in the www.conf area under this one.

Paste the www.conf into the `/etc/opt/remi/php71/php-fpm.d/www.conf`