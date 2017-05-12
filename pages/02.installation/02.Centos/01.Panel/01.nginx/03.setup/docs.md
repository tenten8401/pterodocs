---
title: Setup
taxonomy:
    category: docs
---

Grab the [nginx ssl config](/general/webserver/nginx/ssl) from in the general area

Paste the nginx config of choice into the `/etc/nginx/conf.d/pterodactyl.conf`

#### Configure php-fpm
```

nano /etc/opt/remi/php71/php-fpm.d/www.conf
```

##### Paste the following into the conf
```
[www]

user = nginx
group = nginx

listen = /var/run/php-fpm.sock

listen.owner = nginx
listen.group = nginx
listen.mode = 0750

pm = ondemand
pm.max_children = 9
pm.process_idle_timeout = 10
pm.max_requests = 200
slowlog = /dev/stdout
request_slowlog_timeout = 60s
catch_workers_output = yes
```