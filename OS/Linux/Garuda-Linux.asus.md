# I) Pre-Install

- ## ISO
Get iso from [builds.garudalinux.org](builds.garudalinux.org)

- ## Disk Management
Erase Disk (when installing), okay?

- ## Preventing the System Panic
ALways make sure that the zen kernel is loaded from SHUTDOWN and NOT REBOOT.

# II) Post-Install

~~The first reboot might (or will) cause a system panic (probably due to the zen kernel). Nothing much I can do 🥲~~

# First Steps

1. Connect to the internet
2. Run the setup assistant (completely)
3. Dont let the system go to sleep while pacman (lol)

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
`systemctl start battery-charge-threshold.service`<br>
`systemctl enable battery-charge-threshold.service`

- ## Linux Kernel

`sudo micro /etc/pacman.conf`
```
[g14]
SigLevel = DatabaseNever Optional TrustAll
Server = https://arch.asus-linux.org
```
`sudo pacman -Suy`<br>
`paru linux-g14`<br>
`sudo grub-mkconfig -o /boot/grub/grub.cfg`
