---
title: www.conf
taxonomy:
    category:
        - docs
---

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