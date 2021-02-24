---
title: ODrive Arduino Instructions
tags: [tutorials]
keywords: 
last_updated: September 24, 2020
summary: 
sidebar: mydoc_sidebar
permalink: arduino_odrive_instructions.html
folder: mydoc
---

## Download Arduino script and run serial monitor commands

1. DownloadArduino ODrive header file and script from here. [link](https://github.com/shinerboy/ODrive-Arduino/tree/master/ODriveArduinoTest02)
2. Connect Arduino to computer and upload script.
3. Connect ODrive to Arduino via RX TX pins and ground.
4. Power ODrive
5. Open the serial monitor on the Arduino IDE (ctrl+shift+m)
6. Change baud rate on the serial monitor to 115200
7. Type the number "0" or "1" to begin motor calibration of motors 0 or 1.
8. Once Calibration is complete the motor is ready to be used in closed-loop control.
    * Serial commands are, "s": start sinosoidal motion, "t" stop motion, "u" set speed, "a" set amplitudea