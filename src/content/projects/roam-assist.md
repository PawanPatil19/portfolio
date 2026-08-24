---
title: 'RoamAssist'
description: 'A mobile remote and ROS control layer for safely navigating a quadruped robot assistant.'
pubDate: 'May 02 2023'
stack: ['Flutter', 'Dart', 'C++', 'ROS', 'Unitree SDK']
github: 'https://github.com/PawanPatil19/RoamAssist'
featured: false
---

RoamAssist combines a Flutter mobile interface with ROS and C++ control nodes to navigate a Unitree quadruped as an assistant robot.

## Control system

The ROS layer publishes navigation goals, translates velocity commands for the Unitree SDK, and tracks planned paths. A leash-style controller can change direction and speed, toggle movement, and switch the robot between standing and sitting states.

Safety logic clamps velocity and can stop motion when joystick or ultrasonic inputs signal a hazard. The mobile client provides a simple path for sending commands to the robot over the local network.

## What I learned

Working across a mobile UI, ROS messages, physical sensors, and robot motion made graceful failure and explicit safety states first-class design concerns.
