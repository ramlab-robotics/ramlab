---
title: Low-level API
tags: [tutorials, digit, example, lowlevel api]
keywords: 
last_updated: March, 11, 2021
summary: 
sidebar: mydoc_sidebar
permalink: /digit_lowlevel_api.html
folder: mydoc
---

## Building the Low Level API Example

The following instructions assume a Linux system (or the Windows Subsystem for Linux).

1. Extract the source code from the archive linked at the top of the page

2. Open a terminal in the folder created from the archive (lowlevelapi)

3. Build the example by typing the command make in the terminal

4. Run the example by typing ./lowlevelapi_example (You may need to first set execute permissions by typing chmod +x lowlevelapi_example)

5. If the example is running properly, you should see the following in the terminal:

```
Sending commands to 127.0.0.1 on port 25500
Listening for data from 0.0.0.0 on port 25501
```
## Running the Example in Simulation

1. Run the simulator with both the **lowlevelapi_example.toml** and **lowlevelapi_example_teststand.toml** configuration files applied. Use the following command inside of the main folder ``./ar-control-2021.02.11 'simulator.dynamic = true' ./lowlevelapi/examples/lowlevelapi_example.toml ./lowlevelapi/examples/lowlevelapi_example_teststand.toml``
 The simulator should display the following message in the terminal:

```
Agility Robotics Control Stack
Listening for low-level action data at port 25500
JSON message API server started, connect to http://localhost:8080/
```
2. Open a web browser and navigate to http://localhost:8080/gamepad

3. You should see the robot fixed upright in place with its limbs relaxed

4. Run the Low-level API example code as described in the previous section

5. The terminal running the simulator should display the message Publishing low-level observation data to 127.0.0.1:25501

6. Using the message-composer in another window, send an action-set-operation-mode to set the operation mode to low-level-api. ``["action-set-operation-mode", {"mode": "low-level-api"}]``

7. The robot in the visualization should move into the pose shown below

{% include inline_image.html file="digit_lowlevel_api.png" %}

## Running the Example in Hardware

1. Connect ethernet cable to Digit and computer
2. Apply the ``lowlevelapi_example.toml`` configuration file to Digit by going to http://10.10.1.1/configuration/ and uploading the file
- Due to bug in the configuration browser, the file must be uploaded via ssh (see ssh page for more details)TODO: add ssh page link
- Robot must be rebooted to apply changes
3. Modify the publisher_adress variable in lowlevelapi_example.c so it matches the following: ``const
char* publisher_address = "10.10.1.1";``
4. Rebuild the example program
5. Turn on the robot
6. When the robot has finished booting and you can view the visualization on the gamepad, release the e-STOP to
enable motor torques
- If you wish to use the simple terminal instead of gamepad go to: http://10.10.1.1:8080/examples/terminal.html
7. Run the lowlevelapi_example code
8. Set command priveleged by sending the following mesage in the mesage composer: ``["request-privilege", {"privilege": "change-action-command"}]`` in the simple terminal
9. Using the message-composer, send an action-set-operation-mode to set the operation mode to low-level-api. ``["action-set-operation-mode", {"mode": "low-level-api"}]``
10. The robot should move into the same pose as in simulation


