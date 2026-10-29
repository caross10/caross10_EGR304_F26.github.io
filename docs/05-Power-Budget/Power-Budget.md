---
title: Power Budget
---

## Overview

A power budget was prepared for the Optical Sensor Monitoring and Fault Detection subsystem of the Automatic Pet Food Dispenser to determine the current requirements of the major components and verify that the selected power supply can support the circuit. The budget identifies the electrical requirements of the TCST1103 optical sensor, MCP6004 operational amplifier, PIC18F57Q43 Curiosity Nano board, indicator LEDs, push button, and L7805CV voltage regulator. The subsystem operates using a regulated 5 V power rail supplied by the L7805CV voltage regulator. A rechargeable 8.4 V NiMH battery (NIMH-9V250-1B) serves as the external power source. The current requirements of the components were totaled to determine the required current for the 5 V rail. A 25% safety margin was then included to account for additional current demand and variations during operation. The power budget also evaluates the remaining current available from the regulator and estimates battery operating life based on the values entered in the spreadsheet.

![Power Budget](Power%20Budget%20304.png)

## Conclusions

From the prepared power budget, the subsystem has a calculated total current requirement of 942 mA on the +5 V power rail. After applying a 25% safety margin, the required current increases to 1,177.5 mA. The selected L7805CV voltage regulator has a listed maximum current capacity of 1,500 mA, leaving 322.5 mA of remaining current capacity based on the budget. The external power source selected for the subsystem is the NIMH-9V250-1B rechargeable NiMH battery, which has a nominal output voltage of 8.4 V and a listed capacity of 250 mAh. The power budget estimates a battery operating life of approximately 11.36 hours using the calculated battery current of 44.03 mA. Overall, the power budget provides an estimate of the subsystem's electrical requirements and indicates that the selected regulator has sufficient listed current capacity for the calculated 5 V load. The battery life estimate provides an initial reference for expected operating time and can be used to evaluate the power supply during prototype testing.

## Resources

The completed power budget is available in the following formats:

- [*Power Budget PDF*](Power%20Budget%20304.pdf)
- [*Power Budget Excel Spreadsheet*](Power%20Budget%20304.xlsx)
