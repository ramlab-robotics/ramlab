---
title: Mujoco Startup
tags: [tutorials mujoco example]
keywords: 
last_updated: March, 9 2021
summary: 
sidebar: mydoc_sidebar
permalink: /mujoco_startup.html
folder: mydoc
---

Download Mujoco200 [here](https://www.roboti.us/)

Save the license file inside of ``/mujoco200_linux/bin``

``cd`` into ``/mujoco200_linux/bin`` and type the command ``./simulate ../model/humanoid.xml``

**The following must be done to run the digit simulator in Dynamic mode**

* Create a ``home/.mujoco`` directory (``mkdir .mujoco ``).

* Move the ``/mujoco200_linux`` folder into ``/.mujoco``.

* Copy the license key file (``mjkey ``) inside of ``./mujoco``.


* To run the simulator in dynamic mode run ``./ar-control-xxx.xx.xx 'simulator.dynamic = true' ``

## Installation Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/xG8oujhD9lA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


