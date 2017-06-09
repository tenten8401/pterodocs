---
title: Databases
---

!!! Backup Your Database
!!! The upgrade from `0.5.x` to `0.6.0` includes some rather significant database changes. While the migration utility is able to handle everything for you, we still suggest taking a backup of your database before proceeding just incase.

## Update Database Structure
Run the command below to update the current database structure for the panel.
```sh
php artisan migrate --force
```

## Update Services and Service Options
We've updated our scripts to automatically update services, service options, and variables to match database changes, as well as keep all the defaults available. You'll need to run the command below to re-seed the database with that information.

!!! Running `db:seed` below *will* overwrite any changes you made to core Pterodactyl Services, Service Options, or Variables! This is unavoidable, and this seeder *must* be run. To avoid this in the future, please create custom services or service options.

```sh
php artisan db:seed --force
```

## Set Permissions
The last step is to set the proper owner of the files to be the user that runs your webserver. In most cases this is `www-data` but can vary from system to system — sometimes being `nobody` or `apache`.

[ui-tabs position="top-left" active="0" theme="lite"]
[ui-tab title="nginx"]
```
chown -R www-data:www-data *
```
#### If using CentOS do:
```
chown -R nginx:nginx *
```
[/ui-tab]
[ui-tab title="Second Tab"]
```
chown -R www-data:www-data *
```
#### If using CentOS do:
```
chown -R apache:apache *
```
[/ui-tab]
[/ui-tabs]

## Site Online
Congratulations, you're all finished with the upgrade, run the command below to bring your site back online.
```sh
php artisan up
```

After bringing your panel back online, run the command below to restart you queue workers and ensure they receive the newest settings.

```
php artisan queue:restart
```

! You **must** update your daemons to **`v0.4.0-rc.1`** or later in order to use this version of the panel.

!! If you are upgrading from a version of the panel prior to `0.6.0-beta.1` you will need to re-create any API keys currently in use as the API has ben refactored to use a different permissions system.

## Rebuild Servers

!!! You only need to run this rebuild function if upgrading from a version of the panel **prior to `v0.6.0-pre.6`**.

This next step can take place before or after you update your daemons, it is entirely up to you, however it is **required**. We need to update the daemon configurations to make use of the new service options and docker containers (as well as startup command). Make sure your daemon's are all online to do this.
```sh
php artisan pterodactyl:rebuild --all
```