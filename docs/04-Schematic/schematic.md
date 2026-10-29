---
title: Schematics
---

## Overview

This schematic represents the optical sensor monitoring and fault detection subsystem of the Automatic Pet Food Dispenser. The circuit uses a Vishay TCST1103 optical slot sensor to detect movement of the dispensing mechanism by sensing when an object passes through its optical path. The sensor output is routed through the signal-conditioning circuitry to the PIC18F57Q43 Curiosity Nano microcontroller, which monitors the signal to help identify dispensing activity and potential faults. The subsystem includes an L7805ABV voltage regulator to provide a 5 V supply, resistors and capacitors for current limiting, signal conditioning, and power stabilization, and two indicator LEDs with current-limiting resistors to provide visual feedback during operation. A push button is included specifically for debugging and testing the subsystem during development. Test points allow key signals to be accessed for measurement and troubleshooting, while connectors provide electrical connections between the microcontroller and the other subsystems of the Automatic Pet Food Dispenser. Together, these components enable the subsystem to monitor the dispensing mechanism, support debugging, and provide feedback to the main control system.

![schematic](Subsystem%20Schematic%20Design.png)

**Figure 1:** Showing the individual timer/scheduler subsystem schematic.

## Resources

The schematic as a PDF download is available [*here*](Subsystem%20Schematic%20Design.pdf), and the ZIP folder of the project is available [*here*](Subsytem%20Schematic%20Design.zip).
