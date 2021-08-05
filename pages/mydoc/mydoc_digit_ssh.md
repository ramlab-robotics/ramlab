---
title: SSH Procedure
tags: [tutorials, digit, example, ssh]
keywords: 
last_updated: August, 04, 2021
summary: 
sidebar: mydoc_sidebar
permalink: /digit_ssh.html
folder: mydoc
---

## Secure Shell (SSH)
Provides a way to access a remote terminal session on the robot’s computer and copy files to and
from the robot. assword authentication is disabled, but a unique SSH key is distributed with each robot allowing
access using the root user account.

To SSH without config:
* cd to folder containing SSH key file. File name is titled ``digit014``
* In terminal type the command ``ssh -i digit_ssh_key root@10.10.1.1``
* You are now inside Digit's computer

To set up SSH config for quicker access:
* To avoid having to specify the key in every command, put the key in ``~/.ssh/digit014`` add the following to ``~/.ssh/config`` (create this file
if it does not exist):
```
Host digit
HostName 10.10.1.1
User root
IdentityFile ~/.ssh/digit014
```
* After the above setup, you should be able to log into the robot by running ``ssh digit`` from any directory.

To copy files from digit to Local computer:
* Connect to the robot's network through ethernet or wifi
* Run the command ``scp digit:/agility/conf/lowlevelapi_arms_test.toml /destination/directory`` to copy to specific directory or ``scp digit:/file/location ./`` to copy to current directory

Print out file contents via SSH:
* Run the command ssh digit to start a remote terminal session on the robot’s operating system.
* Run ``cat /file/location`` in the remote terminal session to print out the contents of
the file on the robot’s filesystem.
* Run exit in the remote terminal session to quit and get back to the local system terminal.
