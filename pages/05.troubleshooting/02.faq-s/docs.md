---
title: 'FAQ''s'
---

# Panel says "Unable to connect to Socket.io"
This error is most commonly displayed when there is a misconfiguration for the node that this server is assigned to. In many cases, it is because an administrator setup the node to run using SSL, but has not properly enabled SSL on the daemon.

### Troubleshooting List
Please run through the following list in order to troubleshoot this issue.

0. Make sure if the daemon is properly installed and the active config (`core.json`) matches your config shown in the nodes settings in the panel.

1. Check if the daemon is running. This can be done with `systemctl status wings` if you setup a `systemd` script to boot it (most users).

2. Check if the daemon ports are open in your firewall. The daemon uses ports `8080` and `2022` by default.
```
netstat -tunlp | grep 8080
```
3. Check if your panel can reach the daemon with the FQDN you configured (`tracepath` / `ping` / `nslookup` / `curl`)

4. Check your DNS settings and ensure the DNS has propagated and is correct.
```
nslookup panel.example.com
nslookup daemon.example.com
```
5. Check what the output of your browser console F12 as the console shows the issue in most cases. If you're unsure what the error means, try Googling it first and then ask in Discord if that isn't helpful.

6. Check if you setup the daemon and correctly implemented the `core.json` contents. This is often a major factor if you enable or disable `https` in the panel but don't update the `core.json` file, or vice versa.

7. If you use CloudFlare® make sure that the "Cloud Mode" (orange cloud) for your daemon's A record is disabled. If you want to continue using Cloud Mode, ensure your daemon is configured to listen on `8443` rather than `8080` if you have SSL enabled.

8. Stop the daemon and do `cd /srv/daemon; sudo npm start` to check for errors during boot.

9. Make sure your server is connected to the inter/intranet and is reachable from your computer.

10. Make sure when using the daemon behind a firewall (like `pfSense` or `OpenSwitch`) that you have the correct NAT settings to access your daemon's ports from the outside network.

11. If nothing works: Check your own DNS or connection by doing a  `nslookup` on your associated panel and daemon domains. Also consider using [Google DNS](https://developers.google.com/speed/public-dns/).

12. Sometimes when running the panel and daemon on one server it can help if you add an entry your servers `/etc/hosts` file that redirects your daemons domain to your server itself.

13. Same as above, sometimes the reverse way is also needed, so in some cases you need to add an entry to your servers `/etc/hosts` file that points your panels domain to the correct IP.

14. When running daemon and panel on separate VM's on the same adapter, make sure your VM's can connect to each other (promiscuous mode might be needed).

# MySQL Server Has Gone Away
```
Next Doctrine\DBAL\Driver\PDOException: SQLSTATE[HY000]: General error: 2006 MySQL server has gone away in /home/www/html/pterodactyl/vendor/doctrine/dbal/lib/Doctrine/DBAL/Driver/PDOConnection.php:59
```

If you receive an error similar to the one above, you will need to edit your MySQL configuration to increase the maximum packet size. To do so, edit `/etc/my.cnf` (or applicable file location), to include the following.
```sh
[mysqld]
max_allowed_packet = 64M
```

Then restart MySQL and you should be all set.

# Driver Failed Programming External Connectivity on Endpoint
```
Error: (HTTP code 500) server error - driver failed programming external connectivity on endpoint: 
Error starting userland proxy: listen tcp 172.18.0.1:25565: bind: cannot assign requested address
```

This error almost always occurs when you try to bind an IP address that does not exist on the physical system to the server. The easiest way to check if this is the case is to run the command `ifconfig` which should output something similar to below. Look for `eth0` as that is most likely the public facing IP for your server.

```
root@local:~# ifconfig
eth0   Link encap:Ethernet  HWaddr 04:01:28:e9:e7:01  
          inet addr:104.131.60.11  Bcast:104.131.63.255  Mask:255.255.192.0
          inet6 addr: fe80::601:28ff:fee9:e701/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:143006833 errors:0 dropped:91 overruns:0 frame:0
          TX packets:150246302 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:54799269309 (54.7 GB)  TX bytes:112087011722 (112.0 GB)
```

You'll notice **inet addr:104.131.60.11** above, indicating that the public facing IP for this server is `104.131.60.11`. This is the IP that you should assign to servers. You will need to remove every instance of the broken IP that is allocated to your particular server or it will continue to fail to build.

Some environments might have a private IP assigned that you will need to use. This is common on systems like Amazon AWS or Google Compute Cloud. If this is the case, assign that IP for allocations, and then use the IP Alias tools to denote the IP that users should use to connect.

If you need more help with this simply [contact us via Discord](https://pterodactyl.io/discord).