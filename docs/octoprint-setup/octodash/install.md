---
title: Install
parent: OctoDash
nav_order: 1
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

[OctoDash Github](https://github.com/UnchartedBull/OctoDash)

[@ChrisRiley Installation Video](https://m.youtube.com/watch?v=kwo3HMBnqC4)