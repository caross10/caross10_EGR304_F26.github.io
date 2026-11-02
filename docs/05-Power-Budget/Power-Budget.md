---
title: Power Budget
---

## Overview

A power budget was prepared for the Optical Sensor Monitoring and Fault Detection subsystem of the Automatic Pet Food Dispenser to determine the current requirements of the major components and verify that the selected power supply can support the circuit. The budget identifies the electrical requirements of the TCST1103 optical sensor, MCP6004 operational amplifier, PIC18F57Q43 Curiosity Nano board, indicator LEDs, push button, and L7805CV voltage regulator. The subsystem operates using a regulated 5 V power rail supplied by the L7805CV voltage regulator. A rechargeable 8.4 V NiMH battery (NIMH-9V250-1B) serves as the external power source. The current requirements of the components were totaled to determine the required current for the 5 V rail. A 25% safety margin was then included to account for additional current demand and variations during operation. The power budget also evaluates the remaining current available from the regulator and estimates battery operating life based on the values entered in the spreadsheet.

![Power Budget](Power%20Budget%20304.PNG)

## Conclusions

The power budget analysis indicates that the Automatic Pet Feeder's optical sensor monitoring subsystem can operate within the available power capacity of the selected 5V power supply. The estimated current consumption of the components connected to the 5V rail is 203 mA. Including a 25% safety margin, the total required current is 253.75 mA. The L7805CV voltage regulator, rated for up to 1.5 A, provides sufficient current capacity for the subsystem while leaving approximately 1,246.25 mA available. The selected external DC power source, rated at 5 A, also provides ample capacity to support the regulator and connected components. Based on these calculations, the power requirements are within the available supply capacity, with sufficient additional current available for reliable operation and potential future expansion.

## Resources

The completed power budget is available in the following formats:

- [*Power Budget PDF*](Power%20Budget%20304.pdf)
- [*Power Budget Excel Spreadsheet*](Power%20Budget%20304.xlsx)
