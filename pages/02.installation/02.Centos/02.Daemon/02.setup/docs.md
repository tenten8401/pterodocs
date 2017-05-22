---
title: Setup
---

#### Download the Wings daemon files and install

```
mkdir -p /srv/daemon /srv/daemon-data
cd /srv/daemon
curl -Lo v0.4.0.tar.gz https://github.com/Pterodactyl/Daemon/archive/v0.4.0.tar.gz
tar --strip-components=1 -xzvf v0.4.0.tar.gz
npm install --only=production
```