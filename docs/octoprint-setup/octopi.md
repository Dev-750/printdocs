---
title: OctoPi
parent: OctoPrint Setup
nav_order: 1
layout: page
---

# Writing the OctoPi Image

## Materials and Equipment

- Micro SD card retrieved from the 3D Printer's Raspberry Pi
- Micro SD to SD adapter
- A Windows or Linux machine with internet access

## Steps

1. You will need to Format the Raspberry Pi's SD card or get another micro SD (8-32GB). It must be FAT32.
2. Install the Raspberry Pi Imager. On a debian terminal you can use `sudo apt install rpi-imager`
3. In the Imager, set the OS under "Other (Specific)" -> "3D Printing" -> select "OctoPi (Stable)"
4. Configure image options
	1. Set Hostname, Username, and Password
	2. Wifi connection
	3. Location
	4. Keyboard layout
5. Write the image to the SD card
6. Remove sd adapter from machine
7. Remove micro SD from SD adapter
8. reinsert micro SD into the micro SD card slot on Raspberry Pi
9. Reassemble case

## Links

- [More instructions on OctoPrint.org](https://octoprint.org/download/)
- [OctoPi Github](https://github.com/guysoft/OctoPi)