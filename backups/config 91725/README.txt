Voron 2.4 Config (Split Layout)
================================

Folder structure:
-----------------
printer.cfg
hardware/
    mcu.cfg
    steppers.cfg
    fans.cfg
    sensors.cfg
macros/
    start_end.cfg
    calibration.cfg
extras/
    lights.cfg
    buzzer.cfg

How it works:
-------------
- Klipper always loads printer.cfg first.
- printer.cfg has [include ...] lines that point into hardware/, macros/, and extras/.
- This keeps everything clean and modular.

What YOU must edit:
-------------------
1. In hardware/mcu.cfg
   - Replace "serial:" under [mcu] with your Octopus by-id string.
   - Replace "canbus_uuid:" (or serial) under [mcu ebb36] with your EBB36 ID.

2. In hardware/sensors.cfg
   - Replace "serial:" under [beacon] with your Beacon by-id string.
   - Measure and set correct x_offset and y_offset for your probe mount.

3. Optional:
   - Adjust run_current values in steppers.cfg if motors run too hot or skip.
   - Update fan pin assignments if your wiring differs.

Usage:
------
Drop the whole folder structure into ~/printer_data/config/ on your Klipper Pi.
Restart Klipper after making edits.

