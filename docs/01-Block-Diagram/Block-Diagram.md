---
title: Individal Block Diagram
tags:
- EGR 304
- Block Diagram
---

## Overview
The purpose of this individual block diagram is to show the Timer/Scheduler subsystem for Team 101's Automatic Pet Food Dispenser. The subsystem uses a 5 V regulated power supply and a PIC18F57Q43 Curiosity Nano as the primary microcontroller. The Timer/Scheduler uses a clock/timer circuit to generate a timing signal that is conditioned by an MCP6004-I/P operational amplifier before being read by the PIC through an ADC input. A push button provides a digital user input to the microcontroller. Connections to the other team subsystems are provided through the designated connectors. The Timer/Scheduler subsystem communicates with the other team subsystems to coordinate the scheduled dispensing of food.

## Block Diagram 
![Individual Block Diagram](Individual%20Block%20Diagram.png)


