# Web servers related commands

## Apache

**Fix write/read permissions of the document root folder**

To best share with multiple users who should be able to write in `/var/www`, it should be assigned a common group. 

For example the default group for web content on __Ubuntu__ and __Debian__ is `www-data`. 

Make sure the user who need write access to `/var/www` are in the `www-data` group:

```
$ sudo usermod -a -G www-data <USER>
```

Set the correct permissions on `/var/www`:

```
$ sudo chgrp -R www-data /var/www
$ sudo chmod -R g+w /var/www
```

Additionally, make the directory and all directories below it "set GID", so that all new files and directories created under `/var/www` are owned by the `www-data` group.

```
$ sudo find /var/www -type d -exec chmod 2775 {} \;
```

Find all files in `/var/www` and add read and write permission for owner and group:

```
$ sudo find /var/www -type f -exec chmod ug+rw {} \;
```
