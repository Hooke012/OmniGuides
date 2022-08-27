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

# 2. Portmaster:

```
mkdir -p ~/Git
cd ~/Git
git clone https://github.com/safing/portmaster-packaging
cd portmaster-packaging/linux
makepkg -is
sudo systemctl daemon-reload
sudo systemctl enable --now portmaster
sudo cp /opt/safing/portmaster/portmaster_notifier.desktop ~/.config/autostart/
```

# Reboot

# 3. paru (git the better)

```
paru backintime
paru bleachbit
paru electronmail
paru flameshot
paru kotatogram
paru noisetorch
paru nyrna
paru pdfarranger
paru protonvpn-gui
paru touchpad-indicator
paru whatsie-git
paru xclicker
paru webcord
```

# 4. Proceed to Set up ALL of the apps

```
cp /usr/lib/firedragon/firedragon.overrides.cfg ~/.firedragon/firedragon.overrides.cfg
```
