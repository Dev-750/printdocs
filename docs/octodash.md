---
title: OctoDash
nav_order: 5
layout: page
---

# Installing OctoDash

Since this printer comes with a touch screen, you might as well have a GUI on it. OctoDash gives you access to key controls right from the touch screen

1. Update the system: `sudo apt update`
2. Upgrade packages; `sudo apt upgrade`
3. Enable Auto-login console in `raspi-config`
4. Reboot: `sudo reboot`
5. Use the script below to Install OctoDash

This script is also on the OctoDash Github

```bash
bash <(wget -qO- https://github.com/UnchartedBull/OctoDash/raw/main/scripts/install.sh)
```

6. Follow the selection prompts. The last prompt will reboot the Pi

## Links
- [OctoDash Github](https://github.com/UnchartedBull/OctoDash)
- [@ChrisRiley Installation Video](https://m.youtube.com/watch?v=kwo3HMBnqC4)

# Configuring Touchscreen Drivers

The screen is a generic HDMI resistive/capacitive touch display that is connected via SPI.

1. `sudo raspi-config` -> Interface Options -> SPI -> Enable -> Reboot
2. Enter the config file `sudo nano /boot/firmware/config.txt`
3. Add the following to the bottom of the file: 

```
dtoverlay=ads7846,cs=1,penirq=25,penirq_pull=2,speed=50000,keep_vref_on=0,swapxy=0,pmax=255,xohms=150,xmin=200,xmax=3900,ymin=200,ymax=3900
```

4. Save (`Ctrl+O`, `Enter`) and exit (`Ctrl+X`), then reboot (`sudo reboot`)