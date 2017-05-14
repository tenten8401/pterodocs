---
title: Setup
taxonomy:
    category:
        - docs
---

#### Configure pterodactyl.conf
Grab the [nginx ssl config](pterodactyl-conf) in the pterodactyl.conf area under this one.

Paste the nginx config into the `/etc/nginx/conf.d/pterodactyl.conf`

#### Configure php-fpm
Grab the php-fpm [www.conf](php-fpm) in the www.conf area under this one.

Paste the www.conf into the `/etc/opt/remi/php71/php-fpm.d/www.conf`

!! You need to have your MySQL/MariaDB user and table set up before you proceed.

#### Generate application encryption key
```sh

php artisan key:generate --force
```

#### Environment Configuration

The next thing we need to do is get our environment setup for the panel. To do this, run the command below and follow the prompts. Please be aware that the script will first ask if you want to edit a setting (and show the current value). You will need to answer `y` or `yes` to that question before it will ask for the actual data.

```sh

php artisan pterodactyl:env
```

#### Configure mail settings

After you've configured the environment, we need to configure email handling. To do that, enter the command below and follow the prompts. If you would like to use PHP's `mail()` function simply select the `mail` option. You also have the option to use SMTP or an email delivery service.

```sh

php artisan pterodactyl:mail
```

#### Setup database

!! If your database is not set up by now this will error.

We can now setup the database. This is an automatic process that only requires you enter the command below.

```sh

php artisan migrate
```

!!! This command will ask if you are sure you want to continue on a live environment, tell it yes.

Once the database is setup we then need to seed the database with service information. To do so, run the command below.

```sh

php artisan db:seed
```

#### Add Admin Account

Finally, we need to create an admin account on the system. Run the command below and follow the prompts to do so.

```sh

php artisan pterodactyl:user
```

! Passwords for the user must include mixed case, at least one number, and at least 8 characters. The script will fail otherwise.

#### Crontab Setup
We need to setup one cronjob to run every minute so that your server tasks will be queued. Simply run `sudo crontab -e` and then enter the code below at the bottom.

```shell

* * * * * php /var/www/html/pterodactyl/artisan schedule:run >> /dev/null 2>&1
```
