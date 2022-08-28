# Press q

```
paru pi-hole-server
systemctl start pihole-FTL.service
paru php-sqlite
sudo micro /etc/php/php.ini
```

```
[...]
extension=pdo_sqlite
[...]
extension=sockets
[...]
extension=sqlite3
[...]
```

```
paru lighttpd
paru php-cgi
sudo cp /usr/share/pihole/configs/lighttpd.example.conf /etc/lighttpd/lighttpd.conf
systemctl enable --now lighttpd.service
systemctl start --now lighttpd.service
sudo micro /etc/hosts
```

```
127.0.0.1 localhost
127.0.0.1 pi.hole Hookiepath-Garuda
```

# Reboot
