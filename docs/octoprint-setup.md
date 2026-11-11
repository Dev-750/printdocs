---
title: OctoPrint Setup
nav_order: 4
layout: page
---

# OctoPrint Setup

How to install and run OctoPrint on Creator Bot Pro Series II 3D Printers.

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

# Running OctoPrint

**Equipment**: An external USB-A keyboard or a Windows/Linux machine


Now that OctoPi is on the raspberry Pi it will start the OctoPrint server which can be accessed from a browser on the same network to control the printer.

To access OctoPrint, open your browser and type in one of three options:
- `http://octopi.local`
- `http://<custom-hostname>.local`
- `http://<pi's-IP-address>.local`

Using the IP address seems to work the best. To find it type in the Pi's terminal:

```bash
hostname -I
```
*If you do not have an external keyboard, you will need to use SSH, or Putty, etc - See below*

> ### Access Pi via Putty on Windows

> ### Access Pi via SSH on Linux
> 1. Open the terminal appliation and type: 
> ```bash
> 	ssh <username>@<hostname>.local or IP>
> ``` 
> *replace `<username>` and `<hostname>` with those you set earlier.*
> 2. Enter the Pi's user password

Once the interface loads, create an account.

Now you will see all of your printer's metrics and options and be able to control and print from here.