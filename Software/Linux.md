# 1. Setup Assistant:
System Update: Yes

### Post-Install
Printer<br>
Additional KDE Components<br>
AppImage Launcher<br>
Octopi<br>
LibreOffice Fresh<br>
Vivaldi<br>
ThunderBird<br>
VLC<br>
OBS Studio<br>
IntelliJ<br>
VirtualBox<br>

# 2. Pi-Hole

```
paru pi-hole-server
systemctl start pihole-FTL.service
```

# holy frick... press q

```
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

# 3. paru (git the better)

```
paru backintime
paru bleachbit
paru fastfetch
paru flameshot
paru freetube
paru kotatogram
paru noisetorch
paru nyrna
paru pdfarranger
paru protonvpn-gui
paru qbittorrent-enhanced-qt5
paru spotify-tray
paru tesseract-gui
paru touchpad-indicator
paru whatsie-git
paru xclicker
paru webcord
```

# 4. Proceed to Set up ALL of the apps
