---
title: 'Update Webserver'
---

We now allow file uploads for certain actions within the panel. You will need to increase PHP's limits for uploads. The quickest way to do this is editing your webserver configuration and then restarting your web server. Refer to [Webserver Configuration](doc:webserver-configuration) if you don't remember how to restart it, or where the files are. :warning: This step is only necessary if upgrading from `0.5.x`, and can be skipped if it is already in your configuration file.

[ui-tabs position="top-left" active="0" theme="lite"]
[ui-tab title="nginx"]
```
location ~ \.php$ {
    ...
    fastcgi_param PHP_VALUE "upload_max_filesize = 100M \n post_max_size=100M";
    ...
}
```

[/ui-tab]
[ui-tab title="apache"]
```
<VirtualHost *:80>
	...
  php_value upload_max_filesize 100M
  php_value post_max_size 100M
  <Directory "/var/www/pterodactyl/html/public">
  ...
</VirtualHost>
```
[/ui-tab]
[/ui-tabs]