---
title: Octo Pi
parent: Octo Print Setup
layout: page
---

# Writing the Octo Pi Image
1. You will need to Format the Raspberry Pi's SD card or get another micro SD (8-32GB). It must be FAT32.
2. Install the Raspberry Pi Imager. On a debian terminal you can use `sudo apt install rpi-imager`
3. In the Imager, set the OS under "Other (Specific)" -> "3D Printing" -> select "OctoPi (Stable)"
4. Configure image options
	1. Set Hostname, Username, password
	2. Wifi connection
	3. Location
	4. Keyboard layout
5. Write the image to the SD card

## Links
- [More instructions on OctoPrint.org](https://octoprint.org/download/)
- [OctoPi Github](https://github.com/guysoft/OctoPi)