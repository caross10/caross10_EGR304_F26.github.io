---
title: Bill of Materials
tags:
  - EGR 304
  - Automatic Pet Food Dispenser
  - Optical Sensor Monitoring
---

## Overview

This section presents the Bill of Materials (BOM) for Team 101's Optical Sensor Monitoring subsystem for the Automatic Pet Food Dispenser. The BOM identifies the major components and supporting electrical components required to construct the subsystem. It includes component descriptions, quantities, unit costs, total costs, manufacturers, manufacturer part numbers, supplier information, datasheets, and schematic reference designators. The subsystem uses a Vishay TCST1103 optical slot sensor to detect movement of the dispensing mechanism. A Microchip MCP6004-I/P operational amplifier conditions the sensor signal before it reaches the PIC18F57Q43 Curiosity Nano microcontroller. An STMicroelectronics L7805CV voltage regulator provides a regulated 5 V supply. Additional components include resistors, capacitors, LEDs, a pushbutton, a fuse, a DC barrel jack, and a connector for subsystem integration. The optical slot sensor is the only component that still needs to be purchased. All other components listed in the BOM are already available. The listed prices for those components are included for reference, while their additional purchase costs are recorded as $0.00.

## Bill of Materials

*Table 1: Bill of Materials for the Optical Sensor Monitoring subsystem.*

| **Part Name/Description** | **Unit Qty** | **Per Unit Cost** | **Total Cost** | **Manufacturer** | **Manufacturer Part #** | **Supplier** | **Vendor Part Number** | **Datasheet Link** | **Schematic Reference Designators** |
|:---|:---:|---:|---:|:---|:---|:---|:---|:---|:---|
| Optical Slot Sensor, Infrared Emitter and Phototransistor, 3.1 mm Slot Width, Through-Hole Package | 1 | $1.48 | $1.48 | Vishay Semiconductor | TCST1103 | DigiKey | Verify current listing | [Datasheet](https://www.vishay.com/docs/83752/tcst1103.pdf) | Photo Sensor (verify) |
| Quad Operational Amplifier, Rail-to-Rail Input/Output, 1 MHz Gain-Bandwidth Product, DIP-14 Package | 1 | $0.59 | $0.59 | Microchip Technology | MCP6004-I/P | DigiKey | Verify current listing | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/20001733L.pdf) | U? (verify) |
| Fixed 5 V Linear Voltage Regulator, 1.5 A Nominal Output Current, TO-220 Package | 1 | $1.08 | $1.08 | STMicroelectronics | L7805CV | DigiKey | Verify current listing | [Datasheet](https://www.st.com/resource/en/datasheet/l78.pdf) | U? (verify) |
| Red LED, Through-Hole Indicator, 151051RS11000 Series | 1 | $0.00 | $0.00 | Verify manufacturer | 151051RS11000 | Already owned | N/A | Verify datasheet | D2 (verify) |
| Debugging LED, Through-Hole Indicator, 151051RS11000 Series | 1 | $0.00 | $0.00 | Verify manufacturer | 151051RS11000 | Already owned | N/A | Verify datasheet | D1 (verify) |
| Momentary Tactile Pushbutton Switch, Through-Hole Package | 1 | $0.00 | $0.00 | Omron | B3F-4055 | Already owned | N/A | Verify datasheet | SW1 |
| Fixed Resistor, 220 Ω, Optical Sensor Infrared Emitter Current Limiting | 1 | $0.00 | $0.00 | Verify manufacturer | TBD | Already owned | N/A | N/A | R2 |
| Fixed Resistor, 10 kΩ, Phototransistor Load/Pull-Up | 1 | $0.00 | $0.00 | Verify manufacturer | TBD | Already owned | N/A | N/A | R3 |
| Fixed Resistor, 100 Ω, LED Current Limiting | 2 | $0.00 | $0.00 | Verify manufacturer | TBD | Already owned | N/A | N/A | R4, R5 (verify) |
| Ceramic Capacitor, 0.33 µF, Voltage Regulator Input Filtering | 1 | $0.00 | $0.00 | Verify manufacturer | TBD | Already owned | N/A | N/A | C1 |
| Ceramic Capacitor, 0.1 µF, Voltage Regulator Output Filtering | 1 | $0.00 | $0.00 | Verify manufacturer | TBD | Already owned | N/A | N/A | C2 |
| Ceramic Capacitor, 0.1 µF, Microcontroller Bypass | 1 | $0.00 | $0.00 | Verify manufacturer | TBD | Already owned | N/A | N/A | C5 |
| Ceramic Capacitor, 0.1 µF, Optical Sensor Supply Bypass | 1 | $0.00 | $0.00 | Verify manufacturer | TBD | Already owned | N/A | N/A | C3 |
| Fuse, 0.5 A, Power Supply Input Protection | 1 | $0.00 | $0.00 | Verify manufacturer | TBD | Already owned | N/A | N/A | F1 |
| DC Barrel Jack, Through-Hole Power Connector | 1 | $0.00 | $0.00 | Verify manufacturer | PJ-102AH (verify) | Already owned | N/A | Verify datasheet | J1 |
| Pin Header Connector, 1 × 8, Subsystem Interface | 1 | $0.00 | $0.00 | Verify manufacturer | Conn_01x08_Pin | Already owned | N/A | N/A | J2 |
| PIC18F57Q43 Curiosity Nano Development Board, Microcontroller and Digital/Analog I/O | 1 | $0.00 | $0.00 | Microchip Technology | PIC18F57Q43 Curiosity Nano | Already owned | N/A | [Manufacturer documentation](https://www.microchip.com/) | U2 (verify) |

## Cost Summary

The estimated new-purchase cost for the subsystem is $1.48 because the optical slot sensor is the only component that still needs to be purchased.

| **Cost Category** | **Amount** |
|:---|---:|
| Optical slot sensor | $1.48 |
| Other components already owned | $0.00 additional cost |
| **Total Estimated New-Purchase Cost** | **$1.48** |

The reference prices for the three selected major components are:

- TCST1103 optical slot sensor: 1 × $1.48 = $1.48
- MCP6004-I/P operational amplifier: 1 × $0.59 = $0.59
- L7805CV voltage regulator: 1 × $1.08 = $1.08

The combined reference cost of these three major components is $3.15. This amount is not the additional purchasing cost because the operational amplifier and voltage regulator are already owned.

## Notes

- A unit cost of $0.00 indicates that the component is already owned and does not represent its retail value.
- Prices are estimates from the component selection report and may change with supplier pricing and availability.
- Verify manufacturer details, supplier part numbers, quantities, and schematic reference designators against the final KiCad schematic and actual component packaging.
- The PIC18F57Q43 Curiosity Nano is included in the complete component inventory even though it was preselected for the project.
- The subsystem displays an error message and illuminates the red status LED when a fault is detected. It does not directly request that the motor-driver subsystem stop the motor.
