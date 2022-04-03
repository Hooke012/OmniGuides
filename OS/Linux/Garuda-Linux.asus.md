# I) Pre-Install

- ## ISO
Get iso from [builds.garudalinux.org](builds.garudalinux.org)

- ## Disk Management
Erase Disk (when installing), okay?

- ## Preventing the System Panic
ALways make sure that the zen kernel is loaded from SHUTDOWN and NOT REBOOT.

# II) Post-Install

# First Steps

1. Say no to the setup assistant, Do these and then reboot

- ## Linux Kernel

`sudo micro /etc/pacman.conf`
```
[g14]
SigLevel = DatabaseNever Optional TrustAll
Server = https://arch.asus-linux.org
```

```
sudo pacman -Suy
paru linux-g14
sudo micro /etc/default/grub
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

# Reboot

- ## Battery Threshold

```sudo micro /etc/systemd/system/battery-charge-threshold.service ```

```
[Unit]
Description=Set the battery charge threshold
After=multi-user.target
StartLimitBurst=0

[Service]
Type=oneshot
Restart=on-failure
ExecStart=/bin/bash -c 'echo 80 > /sys/class/power_supply/BAT?/charge_control_end_threshold'

[Install]
WantedBy=multi-user.target
```

```
systemctl start battery-charge-threshold.service
systemctl enable battery-charge-threshold.service
```

# [Proceed](https://github.com/Hooke012/OmniGuides/blob/main/Software/Linux.md)
