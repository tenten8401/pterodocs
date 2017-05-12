---
title: Download
---

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