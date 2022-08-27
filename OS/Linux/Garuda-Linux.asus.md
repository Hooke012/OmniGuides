# I) Pre-Install

- ## ISO
Get iso from [builds.garudalinux.org](https://builds.garudalinux.org)

- ## Disk Management
Create the first partition to be 150 gigs (for Garuda) and then 50 gigs for revios and the remanining as raw

# II) Post-Install

# First Steps

1. Minimise the setup assistant, Do these.

- ## Battery Threshold

```
sudo micro /etc/systemd/system/battery-charge-threshold.service 
```

```
[Unit]
Description=Set the battery charge threshold
After=multi-user.target
StartLimitBurst=0

[Service]
Type=oneshot
Restart=on-failure
ExecStart=/bin/bash -c 'echo 60 > /sys/class/power_supply/BAT?/charge_control_end_threshold'

[Install]
WantedBy=multi-user.target
```

```
systemctl start battery-charge-threshold.service
systemctl enable battery-charge-threshold.service
```

# Run the bash files in `~/.config/autostart/`

# [Proceed](https://github.com/Hooke012/OmniGuides/blob/main/Software/Linux.md)
