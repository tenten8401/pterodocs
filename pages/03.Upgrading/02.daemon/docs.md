---
title: Daemon
---

!!! Automatic updater  
!!! If you want to automatically update your daemon on **Ubuntu or Debian** use:
!!! ```
!!! source <(curl -s https://bin.ptdl.co/wode0/)
!!! ```

!! Make sure to stop the daemon before upgrading it. This **does not** affect any game server.
!! ```
!! service wings stop
!! ```

To upgrade from `v0.3.x` or later to `v0.4.0` switch the directory where you installed your daemon to. If you followed the installation guide just run the following command.
```sh
cd /srv/daemon
```

Then you can download the newest release.

```sh
curl -Lo v0.4.1.tar.gz https://github.com/Pterodactyl/Daemon/archive/v0.4.1.tar.gz
```

After doing that, extract the files from the compressed file.
```sh
tar --strip-components=1 -xzvf v0.4.1.tar.gz
```

You will then need to update your `node_modules`.
```sh
npm update --only=production
```

Once you have done that, you can now start Pterodactyl Daemon using `service wings start`.