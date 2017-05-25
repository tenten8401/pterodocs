---
title: 'Download panel files'
taxonomy:
    category:
        - docs
---

####**Composer**
Pterodactyl Panel makes use of [Composer](https://getcomposer.org/) to install dependencies and get everything setup and running for you. In order to use composer, you will first need to install it.
```
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
```
####**Database Configuration**
Pterodactyl Panel will automatically configure your database for you. You will need to have connection details on hand, as well as create **an empty database** for the panel to install to.

####**Setup**
Once you have composer installed you only need to run one command to have the panel run through the installation and setup process.
```
cp .env.example .env
composer install --no-dev
```
When you run the command above it will begin by installing all of the dependencies required by the panel into the `vendor/` directory. It is possible that the installer will encounter a throttle limit from Github (where it is downloading packages from) which will require you to login to your Github account and generate an OAuth token. *The error will walk you through this process if it occurs, do not worry.*

We then need to generate an application encryption key using the command below.

```
php artisan key:generate --force
```
####**Environment Configuration**
!!! MySQL Database  
!!! You will need an existing MySQL database and non-root user to continue with the installation. Please see our Setting Up MySQL tutorial for how to do this if you are unsure.

The next thing we need to do is get our environment setup for the panel. To do this, run the command below and follow the prompts. Please be aware that the script will first ask if you want to edit a setting (and show the current value). You will need to answer `y` or `yes` to that question before it will ask for the actual data.

```
php artisan pterodactyl:env
```
After you've configured the environment, we need to configure email handling. To do that, enter the command below and follow the prompts. If you would like to use PHP's `mail()` function simply select the `mail` option. You also have the option to use SMTP or an email delivery service.

```
php artisan pterodactyl:mail
```

####**Database Setup**
We can now setup the database. This is an automatic process that only requires you enter the command below.

```
php artisan migrate
```

!!! This command will ask if you are sure you want to continue on a live environment, tell it yes.  

Once the database is setup we then need to seed the database with service information. To do so, run the command below.

```
php artisan db:seed
```

####**Add Admin Account**
Finally, we need to create an admin account on the system. Run the command below and follow the prompts to do so.

```
php artisan pterodactyl:user
```
Passwords for the user must include mixed case, at least one number, and at least 8 characters. The script will fail otherwise.

####**Set Permissions**
The last step here is to set the proper owner of the files to be the user that runs your webserver. In most cases this is `www-data` but can vary from system to system — sometimes being `nobody` or `nginx`.
 
 ```
 chown -R www-data:www-data *
 ```