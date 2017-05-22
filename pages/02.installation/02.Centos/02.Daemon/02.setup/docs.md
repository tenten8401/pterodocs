---
title: 'Setup & Start'
---

#### Download the Wings daemon files and install

```
mkdir -p /srv/daemon /srv/daemon-data
cd /srv/daemon
curl -Lo v0.4.0.tar.gz https://github.com/Pterodactyl/Daemon/archive/v0.4.0.tar.gz
tar --strip-components=1 -xzvf v0.4.0.tar.gz
npm install --only=production
```

#### Configure Systemd service

Write the following to the `/etc/systemd/system/wings.service` file

```
[Unit]
Description=Pterodactyl Wings Daemon
After=docker.service

[Service]
User=root
#Group=some_group
WorkingDirectory=/srv/daemon
LimitNOFILE=4096
PIDFile=/var/run/wings/daemon.pid
ExecStart=/usr/bin/node /srv/daemon/src/index.js
Restart=on-failure
StartLimitInterval=600

[Install]
WantedBy=multi-user.target
```

#### Add firewalld rules
Opens ports 8080 and 2022 for the daemon and sftp
```
firewall-cmd --add-port 8080/tcp --permanent
firewall-cmd --add-port 2022/tcp --permanent
firewall-cmd --add-port 8080/tcp
firewall-cmd --add-port 2022/tcp
```

!! Before this next part you need to add the daemon to the panel and write the core.json file.
!! Please check the tutorials node section on how to set up a node.

#### start services
```
systemctl start docker
systemctl enable docker
systemctl start wings
systemctl enable wings
```