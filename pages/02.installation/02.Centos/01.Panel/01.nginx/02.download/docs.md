---
title: Download
taxonomy:
    category:
        - docs
---

#### Get the files from GitHub
```sh
mkdir -p /var/www/html/pterodactyl
cd /var/www/html/pterodactyl/
wget https://github.com/Pterodactyl/Panel/releases/download/v0.6.1/Panel-0.6.1.tar.gz
tar --strip-components=1 -xzvf Panel-0.6.1.tar.gz
```

#### Run Composer
```sh
cd /var/www/html/pterodactyl/
cp .env.example .env
composer install --no-dev
```


#### Copy example env file
```sh
cp .env.example .env
composer install --no-dev
```

#### Set perms on files
```sh
chown -R nginx:nginx /var/www/html/pterodactyl/
chmod -R 777 storage/
```