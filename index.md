---
title: Overview
nav_order: 1
layout: home
---

# SOP: Powering On and Operating the CreatorBot 3D Pro Series II (OctoPrint / OctoDash)

**Document No.:** SOP-3DP-001  |  **Revision:** 1.0  |  **Effective Date:** \[Date\] **Owner:** \[Name / Department\]  |  **Approved By:** \[Name\]

<img src="{{ '/assets/images/cb3dpsii.jpg' | relative_url }}" alt="Screenshot of the dashboard" width="100%" padding="12px">

> **Note:** Items in \[brackets\] are site- or material-specific and should be filled in from your CreatorBot manual and filament manufacturer's data sheet before this SOP is issued.

## 1. Purpose

This procedure defines the safe and consistent method for powering on, preparing, operating, and shutting down the CreatorBot 3D Pro Series II 3D printer controlled by OctoPrint with the OctoDash touchscreen interface.

## 2. Scope

This SOP applies to all personnel authorized to operate the printer. It covers startup, filament handling, print preparation, print monitoring, completion, and shutdown. It does not cover major maintenance, firmware flashing, or OctoPrint server administration.

## 3. Definitions

- **OctoPrint:** Web-based 3D printer control software running on a Raspberry Pi (or similar) connected to the printer.
- **OctoDash:** Touchscreen dashboard that runs on top of OctoPrint and provides on-screen controls.
- **Hotend:** Heated nozzle assembly that melts filament.
- **Build plate / bed:** Heated surface on which the part is printed.
- **G-code:** The sliced file the printer executes.

## 4. Responsibilities

- **Operator:** Follows this SOP, monitors the print, and reports faults.
- **Supervisor:** Ensures operators are trained and that the work area is compliant.
- **Maintenance lead:** Performs scheduled maintenance and corrective repairs.

## 5. Safety Requirements

1. **Burn hazard:** The hotend can exceed \[260 °C\] and the bed can exceed \[100 °C\]. Never touch either while powered or until they have cooled below \[50 °C\].
2. **Moving parts:** Keep hands, hair, loose clothing, and jewelry clear of the gantry, belts, and fans while the printer is active.
3. **Fumes:** Operate in a ventilated area. Materials such as ABS and ASA require adequate ventilation or filtration.
4. **Fire:** Never leave a print unattended without an approved monitoring plan. Keep a \[Class ABC / CO2\] fire extinguisher accessible. Do not store flammable materials near the printer.
5. **Electrical:** Use only a grounded outlet or surge-protected power strip. Do not operate with damaged cords. Keep liquids away from the printer, power supply, and Raspberry Pi.
6. **Tools:** Use the supplied scraper and tools only. Scrape away from the body.
7. **Emergency stop:** Know the location of the printer's power switch and the room's emergency shutoff.

## 6. Required Materials and Equipment

- CreatorBot 3D Pro Series II printer with power cable
- Raspberry Pi running OctoPrint with OctoDash touchscreen, connected by USB to the printer
- Network connection (Wi-Fi or Ethernet) for remote access to OctoPrint
- Filament appropriate for the job, stored dry
- Sliced G-code file
- Build plate scraper, flush cutters, isopropyl alcohol (IPA) and lint-free wipes
- Safety glasses and heat-resistant gloves

## 7. Pre-Operation Inspection

Perform before every power-on:

1. Confirm the work area is clean, ventilated, and free of clutter.
2. Inspect the power cable and USB cable for damage.
3. Check that the build plate is clean, properly seated, and free of leftover prints or debris.
4. Confirm the nozzle is free of visible residue and the print path is clear.
5. Check that the filament spool rotates freely and the filament path is not tangled.
6. Confirm the enclosure door, if equipped, closes properly and the Pi and touchscreen are securely connected.

## 8. Power-On Procedure

1. Plug the printer into the grounded outlet and confirm the Raspberry Pi/OctoDash screen is also powered.
2. Turn on the printer's main power switch.
3. Wait for the Raspberry Pi to boot. OctoDash will display its start screen; allow approximately \[60–90\] seconds.
4. On the OctoDash home screen, confirm the connection status shows the printer is **connected/operational**.
5. If the printer shows **Disconnected**: check the USB cable, then open the OctoPrint web interface (http://\[octopi-address\]) and connect with the correct serial port and baud rate (\[115200\] unless otherwise specified). See Section 14.
6. Confirm the displayed hotend and bed temperatures read near room temperature. Unusual readings (0 °C, very high, or fluctuating) require stopping and notifying maintenance.

## 9. Homing and Bed Check

1. In OctoDash, open **Control** and select **Home** (all axes).
2. Observe movement. The X, Y, and Z axes should move smoothly to their endstops without grinding or binding.
3. If the machine requires bed leveling at this stage, follow the manufacturer's leveling procedure or the site's bed-leveling work instruction. Level whenever the plate is changed, after transport, or when first-layer adhesion degrades.
4. Raise the Z axis to a safe height before loading filament or cleaning the nozzle.

## 10. Loading or Changing Filament

1. Confirm the filament type, diameter (\[1.75 mm\]), and color match the job.
2. In OctoDash, open **Filament** (or **Control**) and select **Preheat**, setting the hotend to the material's recommended temperature (\[PLA \~200 °C / PETG \~235 °C / ABS \~245 °C\]; confirm with the filament data sheet).
3. When the hotend reaches temperature, **unload** any existing filament using the Filament menu **Retract/Unload** function. Do not pull filament by force.
4. Cut the end of the new filament at an angle with flush cutters.
5. Feed the new filament into the extruder until it grips, then select **Load/Extrude**. Continue until clean, correctly colored material flows steadily from the nozzle.
6. Remove purged material from the nozzle with tweezers or the scraper once safe to do so. Wear heat-resistant gloves.
7. Allow the hotend to cool or proceed directly to printing.

## 11. Preparing the Build Plate

1. Ensure the plate is cool before cleaning.
2. Wipe the print surface with isopropyl alcohol and a lint-free wipe. Do not touch the print surface with bare fingers afterward.
3. Apply adhesion aids (glue stick, adhesive spray) only if required by the material and approved for this printer.

## 12. Starting a Print

1. Upload the sliced G-code to OctoPrint through the web interface, or confirm it is already stored in OctoPrint's file list.
2. On OctoDash, select **Print** and choose the correct file.
3. Verify the filename, estimated print time, and filament requirement on the confirmation screen.
4. Confirm the filament amount on the spool is sufficient for the job.
5. Start the print. The printer will preheat the bed and hotend, home, and begin printing.
6. **Watch the first layer.** Remain at the printer for at least the first \[5–10\] minutes. The first layer should be smooth, continuous, and fully adhered. If it is not:
   - Select **Cancel** in OctoDash.
   - Allow the machine to cool, clean the bed, re-level or adjust Z-offset, and restart.

## 13. Monitoring the Print

1. Check progress periodically using OctoDash or the OctoPrint web interface.
2. Watch for warning signs: layers shifting, stringing, curling, spaghetti-like extrusion, grinding noises, burnt smell, smoke, or temperature fluctuations.
3. Use **Pause** for brief interventions, and **Cancel** to stop a failed print. Do not use Pause for extended periods with the hotend hot, as the filament may degrade or clog the nozzle.
4. If a print is left running while the operator is away, follow the site's unattended-print policy: \[define approved conditions, camera, smart-plug auto shutoff, and temperature fault protection\].
5. **Emergency action:** In the event of fire, smoke, or electrical fault, press the printer's power switch to off, unplug the unit if it is safe to do so, evacuate if necessary, and follow site emergency procedures. Notify the supervisor immediately.

## 14. Troubleshooting Quick Reference

| Symptom | Likely Cause | Action |
| --- | --- | --- |
| Printer shows Disconnected in OctoPrint | USB cable, wrong port, or baud rate | Reseat the USB cable, reconnect in OctoPrint, verify port and baud rate |
| OctoDash frozen or blank | Pi or display fault | Restart OctoDash/Pi using the OctoPrint system menu, then reconnect |
| Temperature error or thermal runaway message | Loose thermistor or heater wiring | Power off immediately. Do not restart until maintenance inspects |
| Print will not stick to the bed | Dirty plate, bad leveling, wrong Z-offset | Clean with IPA, re-level, adjust bed temperature or Z-offset |
| Nozzle clog or under-extrusion | Debris, moisture in filament, wrong temperature | Perform a cold pull or nozzle clean per the manufacturer and verify filament is dry |
| Layer shifting | Loose belts or too-high speed | Check belt tension and reduce speeds |
| Filament not feeding | Tangled spool or worn extruder gear | Re-spool, check the extruder tension and gear |

## 15. Print Completion and Part Removal

1. Wait for the print to finish. OctoDash will show it as complete.
2. Allow the bed and hotend to cool. Do not remove the part while the plate is hot unless the material and plate procedure explicitly permit it.
3. Remove the part with the scraper or flex plate technique, keeping hands away from the sharp edge.
4. Remove stray filament and debris from the bed and nozzle area.
5. Inspect the part against requirements and record the outcome in the print log.

## 16. Shutdown Procedure

1. Confirm the hotend temperature has dropped below \[50 °C\] and the bed is cool.
2. Remove or park filament as appropriate for storage, and keep it in a dry container.
3. In OctoDash or OctoPrint, use the **system shutdown** option for the Raspberry Pi before cutting power, to prevent SD card corruption. Wait until the Pi's activity light stops.
4. Turn off the printer's main power switch.
5. Unplug the printer if it will be idle for an extended period.
6. Clean the work area and return tools to their designated location.

## 17. Routine Maintenance (Summary)

- **Per print:** Clean bed, inspect nozzle, confirm filament path.
- **Weekly:** Wipe rods and rails, check belt tension, inspect fans, clear debris from the enclosure.
- **Monthly:** Lubricate motion components per the manual, verify screws and couplers, check wiring and connectors.
- **As needed:** Replace nozzle, PTFE tubing, or build surface when worn. Update OctoPrint plugins and backups per IT policy.

## 18. Records

Maintain a print log recording: date, operator, file name, material, printer settings, result, and any faults or maintenance performed. Retain per \[retention period\].

## 19. References

- CreatorBot 3D Pro Series II manufacturer's user manual
- OctoPrint documentation (octoprint.org)
- OctoDash documentation
- Filament manufacturer's data sheets and safety data sheets (SDS)

## 20. Revision History

| Rev | Date | Description | Author |
| --- | --- | --- | --- |
| 1.0 | \[Date\] | Initial release | \[Name\] |
