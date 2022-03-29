# 1. Pi-Hole

`paru pi-hole-server`<br><br>
~~`systemctl start pihole-FTL.service`<br>~~
~~↘️(If fails)<br>~~
~~`sudo micro /etc/systemd/resolved.conf`~~<br>
~~[Resolve]<br>~~
~~DNSStubListener=no<br>~~
~~`systemctl restart systemd-resolved.service`<br>~~
~~`systemctl restart pihole-FTL.service`<br>~~<br>
`paru php-sqlite`<br>
`sudo micro /etc/php/php.ini`<br>
```
[...]
extension=pdo_sqlite
[...]
extension=sockets
[...]
extension=sqlite3
[...]
```
`paru lighttpd`<br>
`paru php-cgi`<br>
`sudo cp /usr/share/pihole/configs/lighttpd.example.conf /etc/lighttpd/lighttpd.conf`<br>
`systemctl enable --now lighttpd.service`<br>
`systemctl start --now lighttpd.service`<br>
`sudo micro /etc/hosts`
```
127.0.0.1              localhost
~~ip.address.of.pihole~~   pi.hole ~~myhostname~~
```
_Pi-Hole hosting device can also make use of Pi-Hole. Just change DNS settings to only IP address 127.0.0.1_

# 2. TouchPad Indicator

`paru touchpad-indicator`

# 3. Setup Assistant:
System Update: Yes

### Post-Install
AppImage Launcher
Octopi
Discover
LibreOffice Fresh
Vivaldi
ThunderBird
Telegram !!
Discord !!
FDM !!
VLC
OBS Studio
IntelliJ
