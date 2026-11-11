---
title: Touchscreen Drivers
parent: OctoDash
nav_order: 2
layout: page
---

# Configuring Touchscreen Drivers

The screen is a generic HDMI resistive/capacitive touch display that is connected via SPI.

1. `sudo raspi-config` -> Interface Options -> SPI -> Enable -> Reboot
2. Enter the config file `sudo nano /boot/firmware/config.txt`
3. Add the following to the bottom of the file: 
   
```txt
dtoverlay=ads7846,cs=1,penirq=25,penirq_pull=2,speed=50000,keep_vref_on=0,swapxy=0,pmax=255,xohms=150,xmin=200,xmax=3900,ymin=200,ymax=3900
```

4. Save (`Ctrl+O`, `Enter`) and exit (`Ctrl+X`), then reboot
