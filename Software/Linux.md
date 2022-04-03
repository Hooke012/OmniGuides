# TODO

# 1. Setup Assistant:
System Update: Yes

### Post-Install
AppImage Launcher<br>
Octopi<br>
Discover<br>
LibreOffice Fresh<br>
Vivaldi<br>
ThunderBird<br>
Xtreme Download Manager<br>
VLC<br>
OBS Studio<br>
IntelliJ<br>

# 1.5 YAY

`paru yay`

# 2. Pi-Hole

```
yay pi-hole-server
systemctl start pihole-FTL.service
```
~~↘️(If fails)<br>~~
~~`sudo micro /etc/systemd/resolved.conf`~~<br>
~~[Resolve]<br>~~
~~DNSStubListener=no<br>~~
~~`systemctl restart systemd-resolved.service`<br>~~
~~`systemctl restart pihole-FTL.service`<br>~~<br>

```
yay php-sqlite
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
yay lighttpd
yay php-cgi
sudo cp /usr/share/pihole/configs/lighttpd.example.conf /etc/lighttpd/lighttpd.conf
systemctl enable --now lighttpd.service
systemctl start --now lighttpd.service
sudo micro /etc/hosts
```

```
127.0.0.1  localhost
127.0.0.1  pi.hole <hostname>
```

# 2.5 [Unbound](https://docs.pi-hole.net/guides/dns/unbound/)


# 3. yay

```
yay touchpad-indicator-git
yay kotatogram-dev-git
yay webcord
yay freetube
yay pdfarranger
yay protonvpn-gui
yay spotify
yay spotify-tray-git
yay whatsapp-for-linux
yay qbittorrent-enhanced-qt5
yay spicetify-cli-git
yay spicetify-themes-git
```

```
sudo chmod a+wr /opt/spotify
sudo chmod a+wr /opt/spotify/Apps -R
spicetify
spicetify backup apply enable-devtool
spicetify update
```

```
curl -fsSL https://raw.githubusercontent.com/JulienMaille/dribbblish-dynamic-theme/master/install.sh | sh
```

