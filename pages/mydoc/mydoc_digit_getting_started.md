---
title: Getting Started
tags: [tutorials][digit]
keywords: 
last_updated: February, 26, 2021
summary: 
sidebar: mydoc_sidebar
permalink: digit_getting_started.html
folder: mydoc
---



The user manual for Digit's hardware and software can be accessed at [this link](http://localhost:8080/doc/) using a web browser when the simulator is running. This documentcontains instructions for getting the simulator running on your personalcomputer or workstation

## Requirements
# Supported Operating Systems
* Linux (Ubuntu 18.04/20.04, other distributions may also work)
* Windows 10 (requires Windows Subsystem for Linux)
Running the simulator on a computer with any other operating system (e.g.MacOS) requires a Linux virtual machine.

# CPU
Requires an AMD64 processor with AVX support. Most Intel and AMDprocessors released since 2011 will work, with the notable exception of IntelAtom processors.

# Additional
Running the simulator requires basic knowledge of how to run commandsand navigate the filesystem in a Linux terminal.

## Setup
# Linux
1. Download the desired version of the simulator. This is the file named ``ar-control-xxxx.xx.xx``, where the part after ``ar-control`` is the release date and version number. Choose the latest version unless it is necessary to do otherwise. 
2. Open a terminal and navigate to the directory containing the file you downloaded.
3. Run the command ``chmod +x ./ar-control-xxxx.xx.xx`` to allowe xecuting the file as a program.
4. Run the command ``./ar-control-xxxx.xx.xx`` to start the simulator.You should see the text Agility Robotics Control Stack, followed by the release version and some more information.
5. Open [this link](http://localhost:8080/) in a web browser. You should see a page with several links, including a link to the full documentation.
6. Press Ctrl+C in the terminal to stop the simulator when you arefinished.

# Windows 10
1. Install Windows Subsystem for Linux using the instructions [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10). When asked to select a Linux distribution, we recommend Ubuntu 18.04 LTS. WSL 2 is recommended over WSL 1.
2. Download the desired version of the simulator (see step 1 of the Linux instructions) to ``C:\Users\<Username>\Downloads``, where ``<Username>`` is your Windows login username.
3. Open the Ubuntu 18.04 shell from the start menu.
4. Run the command ``cp '/mnt/c/Users/<Username>/Downloads/arcontrol-xxxx.xx.xx' ./``, replacing ``<Username>`` and ``xxxx.xx.xx`` as appropriate. This will copy the simulator into the virtual Linux system.
5. Continue by following the Linux instructions from step 3.

## Troubleshooting
* The simulator crashes with an error message mentioning an "illegal instruction" or similar. This crash may occur immediately when trying to start the simulator, or possibly after the simulator has been running for a while.
- The computer's CPU is not supported. Try running the simulator on a newer computer.
* The simulator fails to start with an error message similar to ``/lib/ x86_64-linux-gnu/libc.so.6: undefined reference to 'clock_gettime@GLIBC_2.17'``.
- The version of glibc on this computer is too old. Try running the simulator on a system with a newer Linux distribution on it. Ubuntu 16.04 is the oldest operating system that we currently maintain support for.
* On Windows 10, the simulator fails to start with an error message mentioning "squashfs" or "FUSE".
- Use ``./ar-control-xxxx.xx.xx --appimage-extract-and-run`` to start the simulator instead. This occurs if you are using WSL 1 instead of WSL 2.
* The simulator is running, but there is no terminal window to shut it down from, and I cannot start a new instance of the simulator.
- Run pkill ar-control in a terminal to terminate the program. Note that the version number should be omitted. This usually happens if you start the simulator by double-clicking on it in the file browser.

