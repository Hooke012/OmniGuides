# PKGBUILD

```
mkdir -p ~/Git
cd ~/Git
git clone https://github.com/safing/portmaster-packaging
cd portmaster-packaging/linux
makepkg -is
sudo systemctl daemon-reload
sudo systemctl enable --now portmaster
```

# Manual 
```
sudo pacman -S libnetfilter_queue libappindicator-gtk3
mkdir -p /opt/safing/portmaster
wget -O /tmp/portmaster-start https://updates.safing.io/latest/linux_amd64/start/portmaster-start
sudo mv /tmp/portmaster-start /opt/safing/portmaster/portmaster-start
sudo chmod a+x /opt/safing/portmaster/portmaster-start
sudo /opt/safing/portmaster/portmaster-start --data /opt/safing/portmaster update
```
## Reboot
```
sudo /opt/safing/portmaster/portmaster-start core
/opt/safing/portmaster/portmaster-start app
/opt/safing/portmaster/portmaster-start notifier
sudo micro /etc/systemd/system/portmaster.service
```
```
[Unit]
Description=Portmaster by Safing
Documentation=https://safing.io
Documentation=https://docs.safing.io
Before=nss-lookup.target network.target shutdown.target
After=systemd-networkd.service
Conflicts=shutdown.target
Conflicts=firewalld.service
Wants=nss-lookup.target

[Service]
Type=simple
Restart=on-failure
RestartSec=10
LockPersonality=yes
MemoryDenyWriteExecute=yes
NoNewPrivileges=yes
PrivateTmp=yes
PIDFile=/opt/safing/portmaster/core-lock.pid
Environment=LOGLEVEL=info
Environment=PORTMASTER_ARGS=
EnvironmentFile=-/etc/default/portmaster
ProtectSystem=true
#ReadWritePaths=/var/lib/portmaster
#ReadWritePaths=/run/xtables.lock
RestrictAddressFamilies=AF_UNIX AF_NETLINK AF_INET AF_INET6
RestrictNamespaces=yes
# In future version portmaster will require access to user home
# directories to verify application permissions.
ProtectHome=read-only
ProtectKernelTunables=yes
ProtectKernelLogs=yes
ProtectControlGroups=yes
PrivateDevices=yes
AmbientCapabilities=cap_chown cap_kill cap_net_admin cap_net_bind_service cap_net_broadcast cap_net_raw cap_sys_module cap_sys_ptrace cap_dac_override cap_fowner cap_fsetid
CapabilityBoundingSet=cap_chown cap_kill cap_net_admin cap_net_bind_service cap_net_broadcast cap_net_raw cap_sys_module cap_sys_ptrace cap_dac_override cap_fowner cap_fsetid
# SystemCallArchitectures=native
# SystemCallFilter=@system-service @module
# SystemCallErrorNumber=EPERM
ExecStart=/opt/safing/portmaster/portmaster-start --data /opt/safing/portmaster core -- $PORTMASTER_ARGS
ExecStopPost=-/opt/safing/portmaster/portmaster-start recover-iptables

[Install]
WantedBy=multi-user.target
```

# ONLY IF NOT!
```
[Unit]
Description=Portmaster Privacy App

[Service]
Type=simple
ExecStart=/opt/safing/portmaster/portmaster-start core --data=/opt/safing/portmaster/
ExecStopPost=-/sbin/iptables -F C17
ExecStopPost=-/sbin/iptables -t mangle -F C170
ExecStopPost=-/sbin/iptables -t mangle -F C171
ExecStopPost=-/sbin/ip6tables -F C17
ExecStopPost=-/sbin/ip6tables -t mangle -F C170
ExecStopPost=-/sbin/ip6tables -t mangle -F C171

[Install]
WantedBy=multi-user.target
```
#
```
sudo systemctl daemon-reload
sudo systemctl enable --now portmaster
```
