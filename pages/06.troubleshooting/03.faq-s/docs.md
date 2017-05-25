---
title: 'FAQ''s'
---

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