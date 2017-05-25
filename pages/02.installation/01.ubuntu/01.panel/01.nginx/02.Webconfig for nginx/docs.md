---
title: 'Webconfig for nginx'
taxonomy:
    category:
        - docs
---

The final step in the install process is to setup your webserver to make your panel publicly accessible.

**Nginx**
If you are using NGINX, simply create a new file called `pterodactyl.conf` and then replace `<domain>` with the IP or Fully Qualified Domain Name (e.x. `panel.example.com`) in the configuration file below.

! NGINX Tutorial Assumes SSL Setup
This tutorial assumes that you will be using SSL on both the panel and daemons for significantly improved communication security between users and the panel. You will need to get a valid SSL certificate which can be done for free by using Let's Encrypt. Please see our Creating SSL Certificates tutorial for how to create these certificates before continuing.