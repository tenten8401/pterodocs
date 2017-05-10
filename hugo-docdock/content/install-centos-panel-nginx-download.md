+++
creatordisplayname = "parkervcp"
creatoremail = "parker@parkervcp.com"
date = "2017-05-07T11:59:31-04:00"
description = ""
lastmodifierdisplayname = "parkervcp"
lastmodifieremail = "parker@parkervcp.com"
tags = ["tag1","tag2"]
title = "Download panel files"

[menu]

  [menu.main]
    identifier = "install-centos-panel-nginx-download"
    parent = "install-centos-panel-nginx"
    weight = 52

+++

#### Get the files from GitHub
```
mkdir -p /var/www/html/pterodactyl
cd /var/www/html/pterodactyl/
wget https://github.com/Pterodactyl/Panel/releases/download/v0.6.0/Panel-0.6.0.tar.gz
tar --strip-components=1 -xzvf Panel-0.6.0.tar.gz
```

#### Run Composer
```
cd /var/www/html/pterodactyl/
cp .env.example .env
composer install --no-dev
```

#### Set perms on files
```
chown -R nginx:nginx /var/www/html/pterodactyl/
chmod -R 777 storage/
```