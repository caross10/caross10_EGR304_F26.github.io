---
title: Power Budget
---

## Overview

A power budget was prepared for the Optical Sensor Monitoring and Fault Detection subsystem of the Automatic Pet Food Dispenser to determine the current requirements of the major components and verify that the selected power supply can support the circuit. The budget identifies the electrical requirements of the TCST1103 optical sensor, MCP6004 operational amplifier, PIC18F57Q43 Curiosity Nano board, indicator LEDs, push button, and L7805CV voltage regulator. The subsystem operates using a regulated 5 V power rail supplied by the L7805CV voltage regulator. A rechargeable 8.4 V NiMH battery (NIMH-9V250-1B) serves as the external power source. The current requirements of the components were totaled to determine the required current for the 5 V rail. A 25% safety margin was then included to account for additional current demand and variations during operation. The power budget also evaluates the remaining current available from the regulator and estimates battery operating life based on the values entered in the spreadsheet.

![Power Budget](Power%20Budget%20304.PNG)

## Conclusions

From the prepared power budget, the total calculated current requirement for the +5 V power rail is 942 mA. After applying the 25% safety margin, the required current increases to 1,177.5 mA. The selected L7805CV voltage regulator has a listed maximum current capacity of 1,500 mA, leaving 322.5 mA of remaining current capacity on the +5 V rail. The selected external power source is the NIMH-9V250-1B rechargeable NiMH battery, which has a nominal output voltage of 8.4 V and a listed maximum current of 250 mA. However, the calculated current required from the battery to supply the regulator is 1,177.5 mA. This exceeds the battery's listed maximum current by 927.5 mA, indicating that the selected battery cannot support the calculated power requirement. The power budget reports an estimated battery life of approximately 0.425 hours. However, this calculation uses a battery capacity of 500 mAh, while the selected battery is identified as a 250 mAh battery. Therefore, the reported battery life should not be considered a reliable operating-time estimate. Overall, the power budget identifies that although the L7805CV regulator has sufficient listed current capacity for the calculated +5 V load, the selected rechargeable battery does not have sufficient current capability to supply the subsystem. A battery with a higher current capacity and discharge rating will be necessary to support the calculated power requirements.

## Resources

The completed power budget is available in the following formats:

- [*Power Budget PDF*](Power%20Budget%20304.pdf)
- [*Power Budget Excel Spreadsheet*](Power%20Budget%20304.xlsx)
