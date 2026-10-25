---
title: Individal Block Diagram
tags:
- EGR 304
- Block Diagram
---

## Overview
The purpose of this individual block diagram is to show the Optical Sensor subsystem for Team 101's Automatic Pet Food Dispenser. The subsystem monitors the dispensing mechanism to help determine whether it is operating correctly and detect potential faults during operation.

The subsystem uses a regulated 5 V power supply and a PIC18F57Q43 Curiosity Nano as its primary microcontroller. A Vishay TCST1103 optical sensor detects changes in the optical path, and its output signal is conditioned by an MCP6004-I/P operational amplifier before being read by the PIC through the RA0/ADC1 input. The microcontroller processes the sensor readings to determine whether the expected operating conditions are being met.

A debugging LED and push button support subsystem testing and troubleshooting, while a separate status LED provides visual feedback to the user about the dispenser's operating condition. If a fault is detected, the subsystem is intended to communicate a stop request to the motor-driver subsystem to prevent continued operation. Connections to the other team subsystems are provided through the designated connector.

## Block Diagram 
![Individual Block Diagram](Individual%20Block%20Diagram.png)


