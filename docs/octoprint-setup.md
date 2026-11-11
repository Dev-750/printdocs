---
title: OctoPrint Setup
nav_order: 4
layout: page
---

# OctoPrint Setup

How to install and run OctoPrint on Creator Bot Pro Series II 3D Printers.

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

---

# Running OctoPrint

Now that OctoPi is on the Pi it will Start the OctoPrint server which can be accessed from a Browser on the same network to control the printer.

1. To access OctoPrint, open your browser and type in one of three options:
- `http://octopi.local`
- `http://<custom-hostname>.local`
- `http://<pi's-IP-address>.local`

Using the IP address seems to work the best. To find it type:
```bash
hostname -I
```
 in the Pi's Terminal. **You will either need a keyboard, SSH, or Putty, etc**

To SSH into the Pi type: 
```bash
ssh <username>@<hostname.local or IP>
``` 
and enter the Password

2. Once the interface loads, create an account.
3. Now you will see all of your printer's metrics and options and be able to control and print from here.