---
title: Simple Simulation Commands
tags: [tutorials, digit, example]
keywords: 
last_updated: February, 26, 2021
summary: 
sidebar: mydoc_sidebar
permalink: /digit_simple_commands.html
folder: mydoc
---

## JSON message format
```
[
  "message-type-name",
  {
    "field1": "value",
    "field2": "value"
  },
  1234
]
```
## JSON message samples

```
["request-privilege", {"privilege": "change-action-command"}]

["action-set-operation-mode", {"mode": "disabled"}]

["action-start", {}]

["action-set-operation-mode", {"mode": "locomotion"}]

["action-set-operation-mode", {"mode": "disabled"}]

["action-set-operation-mode", {"mode": "joint"}]

["action-end-effector-move", {"end-effector": "left-hand", "waypoints": [{"rpyxyz": [0,0,0,0,0,0]},{"rpyxyz": [0,0,0,0,0,0.1]}]}]

["action-end-effector-move", {"end-effector": "left-hand", "waypoints": [{"rpyxyz": [0,0,0,0,0,0]},{"rpyxyz": [0,0,0,0,0.4,-0.2]}]}]

["action-end-effector-move", {"end-effector": "left-foot", "waypoints": [{"rpyxyz": [0,0,0,-0.5,0.4,-1.0]},{"rpyxyz": [0,0,0,0,0.4,-1.0]}]}]

[ "action-sit", {} ]

[ "action-stand", {} ]

["action-set-operation-mode", {"mode": "locomotion"}]

["get-robot-info", {}]

["action-calibrate-imu", {}]
```

```
["action-sequential", {"actions": [
  ["action-goto", {"target": {"xy": [0, 0]}}, 0],
  ["action-goto", {"target": {"xy": [0, 2]}}, 1],
  ["action-goto", {"target": {"xy": [2, 2]}}, 2],
  ["action-goto", {"target": {"xy": [2, 0]}}, 3],
  ["action-goto", {"target": {"xy": [0, 0]}}, 4],
  ["action-sit", {}, 5],
]}]
```

## Digit sim and hardware URL
```
http://localhost:8080/
http://localhost:8080/gamepad/
http://10.10.1.1:8080/gamepad/
http://10.10.1.1:8080/examples/terminal.html

```

