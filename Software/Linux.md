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

# 2. Portmaster when?
```
sudo pacman -S libnetfilter_queue libappindicator-gtk3
mkdir -p /opt/safing/portmaster
wget -O /tmp/portmaster-start https://updates.safing.io/latest/linux_amd64/start/portmaster-start
sudo mv /tmp/portmaster-start /opt/safing/portmaster/portmaster-start
sudo chmod a+x /opt/safing/portmaster/portmaster-start
sudo /opt/safing/portmaster/portmaster-start --data /opt/safing/portmaster update
```

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
paru electronmail
paru fastfetch
paru flameshot
paru freetube
paru kotatogram
paru noisetorch
paru nyrna
paru pdfarranger
paru protonvpn-gui
paru qbittorrent-enhanced-qt5
paru tesseract-gui
paru touchpad-indicator
paru whatsie-git
paru xclicker
paru webcord
```

# 4. Proceed to Set up ALL of the apps
