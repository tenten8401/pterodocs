---
title: Panel
---

Upgrading the panel is a simple process

!! Due to major code refactoring and service changes, anyone running with custom services **cannot update from `0.5.x` to `0.6.0`**. We apologize for the inconvenience, but there were such significant changes that there was no reasonable way to be able to make enough correct assumptions to get these services upgraded and working.

Before beginning to install `v0.6.0` you will need to ensure that your system has the following dependencies up-to-date and meeting the minimum version requirements below.

**Failure to complete this step will result in errors down the road.** Please be aware that the packages listed below for certain PHP components assume you have `PHP 7.1` installed. If you installed this panel using the `0.5.x` guide, chances are that you installed `PHP 7.0`, so please adjust the package names accordingly.

* PHP `>= 7.0.0` — PHP `5.6` is no longer supported, as it [stopped receiving active support](http://php.net/supported-versions.php) at the beginning of 2017, and is only receiving security updates. Laravel `5.5` is also noted to be `PHP7+` only, and thus we are phasing out our `PHP 5.6` support early. *It is recommended that you install `PHP 7.1`, however `PHP 7.0` is still supported, and if that is what you have installed, it is fine.

* MySQL `>= 5.7.0` **OR** MariaDB `>= 10.1.3` — Either version is fine, but must meet the minimum version requirements listed, or systems will fail to work in the panel. **Ubuntu and CentOS systems default to MariaDB `10.0` or `5.5` by default, *please* check the make sure you are up-to-date.** If your system is not, please do so. :warning: See [Updating MariaDB](#section-upgrading-mariadb) below for more information on how to do this.

* PHP `zip` Extension — This can be installed using `php7.1-zip` (Ubuntu) or `php71u-zip` (CentOS). It is required to make use of the new pack manager.

* Memcached **OR** Redis is required to use this panel as we make use of increased caching of DB queries to speed up operations. We recommend installing `redis` following [this handy guide](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-redis-on-ubuntu-16-04) from DigitalOcean — a quick Google search should turn up guides for your specific OS if not using Ubuntu 16.04. If you would prefer to install Memcache, that can be done by installing `memcached` as well as the PHP modules for it: `php7.1-memcached` (Ubuntu) or `php71u-memcached` and `php71u-pear` (CentOS).

Once you have upgraded your components, you'll need to restart either `php71-fpm` if using NGINX, or `httpd` if using Apache.

## Upgrading MariaDB

! This upgrade should go smoothly, but there is always potential for data loss. Ensure you have a proper MySQL backup before continuing!

! This upgrade **is only necessary if using MariaDB `< 10.1`**. Do not perform these actions if you have MariaDB `>= 10.1` or MySQL installed!