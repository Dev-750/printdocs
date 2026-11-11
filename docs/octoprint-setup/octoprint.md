---
title: OctoPrint
parent: OctoPrint Setup
nav_order: 2
layout: page
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