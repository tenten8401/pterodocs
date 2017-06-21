---
title: Files
---

## Maintenance Mode
To prevent any data corruption issues or users hitting broken pages, you should fist put the panel into maintenance mode. To do this, simply run the command below in the panel directory.

```sh
php artisan down
```

The first step in the update process is to download the new panel files from Github. Run the command below to save the file.
```sh
curl -Lo v0.6.2.tar.gz https://github.com/Pterodactyl/Panel/archive/v0.6.2.tar.gz
```
!!!  Verify file entegrity  
!!! Now is a good time to verify the integrity of the panel package. You can verify the GPG signature and verify that the SHA256 Checksum is valid for the download. The SHA256 Checksum for v0.6.2 is `b25e497145fa1a48285783ba4d44e6089b0ea655546aae7f8af55dcf833f5226`.

Next you will need to unpack the archive of files, run the commands below to do so.
```sh
rm -rf resources/views
tar --strip-components=1 -xzvf v0.6.2.tar.gz
rm v0.6.2.tar.gz
```

Finally, you will need to set the correct permissions on your files so that the panel can write logs and caches as necessary.
```sh
chmod -R 755 storage/* bootstrap/cache
```