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
| Optical Slot Sensor, Infrared Emitter and Phototransistor, 3.1 mm Slot Width, Through-Hole Package | 1 | $1.48 | $1.48 | Vishay Semiconductor | TCST1103 | [DigiKey](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TCST1103/2354847) | TCST1103-ND | [Datasheet](https://www.vishay.com/docs/83752/tcst1103.pdf) | U4 |
| Quad Operational Amplifier, Rail-to-Rail Input/Output, 1 MHz Gain-Bandwidth Product, DIP-14 Package | 1 | $0.59 | $0.59 | Microchip Technology | MCP6004-I/P | [DigiKey](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060) | MCP6004-I/P-ND | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/20001733L.pdf) | U1 |
| Fixed 5 V Linear Voltage Regulator, TO-220 Package, 1.5 A Nominal Output Current | 1 | $1.08 | $1.08 | STMicroelectronics | L7805CV | [DigiKey](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964) | 497-1443-5-ND | [Datasheet](https://www.st.com/resource/en/datasheet/l78.pdf) | U3 |
| Fixed Resistor, 100 Ω, LED Current Limiting | 2 | $0.00 | $0.00 | Generic | 100 Ω | [DigiKey](https://www.digikey.com/en/products/filter/chip-resistor-surface-mount/52) | N/A | N/A | R1, R4, R5 |
| Fixed Resistor, 220 Ω, Optical Sensor Emitter Current Limiting | 1 | $0.00 | $0.00 | Generic | 220 Ω | [DigiKey](https://www.digikey.com/en/products/filter/through-hole-resistors/53) | N/A | N/A | R2 |
| Fixed Resistor, 10 kΩ, Phototransistor Load | 1 | $0.00 | $0.00 | Generic | 10 kΩ | [DigiKey](https://www.digikey.com/en/products/filter/through-hole-resistors/53) | N/A | N/A | R3 |
| Ceramic Capacitor, 0.33 µF, Voltage Regulator Input Filtering | 1 | $0.00 | $0.00 | Generic | 0.33 µF | [DigiKey](https://www.digikey.com/en/products/filter/ceramic-capacitors/60) | N/A | N/A | C1 |
| Ceramic Capacitor, 0.1 µF, Voltage Regulator Output Filtering | 1 | $0.00 | $0.00 | Generic | 0.1 µF | [DigiKey](https://www.digikey.com/en/products/filter/ceramic-capacitors/60) | N/A | N/A | C2 |
| Ceramic Capacitor, 0.1 µF, Optical Sensor Supply Bypass | 1 | $0.00 | $0.00 | Generic | 0.1 µF | [DigiKey](https://www.digikey.com/en/products/filter/ceramic-capacitors/60) | N/A | N/A | C3 |
| Ceramic Capacitor, 0.1 µF, Pushbutton Supply Bypass | 1 | $0.00 | $0.00 | Generic | 0.1 µF | [DigiKey](https://www.digikey.com/en/products/filter/ceramic-capacitors/60) | N/A | N/A | C4 |
| Ceramic Capacitor, 0.1 µF, Microcontroller Bypass | 1 | $0.00 | $0.00 | Generic | 0.1 µF | [DigiKey](https://www.digikey.com/en/products/filter/ceramic-capacitors/60) | N/A | N/A | C5 |
| Red LED, Through-Hole Indicator | 2 | $0.00 | $0.00 | Würth Elektronik | 151051RS11000 | [DigiKey](https://www.digikey.com/en/products/detail/w%C3%BCrth-elektronik/151051RS11000/4490012) | 732-5016-ND | [Product information](https://www.we-online.com/en/components/products/151051RS11000) | D1, D2 |
| Momentary Tactile Pushbutton Switch, Through-Hole Package | 1 | $0.00 | $0.00 | Omron | B3F-4055 | [DigiKey](https://www.digikey.com/en/products/detail/omron-electronics-inc-emc-div/B3F-4055/31799) | SW414-ND | [Datasheet](https://omronfs.omron.com/en_US/ecb/products/pdf/en-b3f.pdf) | SW1 |
| Fuse, 0.5 A, Power Supply Input Protection | 1 | $0.00 | $0.00 | Generic | 0.5 A | [DigiKey](https://www.digikey.com/en/products/filter/fuses/139) | N/A | N/A | F1 |
| DC Barrel Jack, Through-Hole Power Connector | 1 | $0.00 | $0.00 | Same Sky | PJ-102AH | [DigiKey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/PJ-102AH/408448) | CP-102AH-ND | [Datasheet](https://www.sameskydevices.com/product/resource/pj-102ah.pdf) | J1 |
| 1 × 8 Pin Header, Through-Hole Subsystem Connector | 1 | $0.00 | $0.00 | Generic | Conn_01x08_Pin | [DigiKey](https://www.digikey.com/en/products/filter/rectangular-connectors-headers-male-pins/314) | N/A | N/A | J2 |
| PIC18F57Q43 Curiosity Nano Development Board | 1 | $0.00 | $0.00 | Microchip Technology | PIC18F57Q43 Curiosity Nano | [DigiKey](https://www.digikey.com/en/products/detail/microchip-technology/DM164150/11586705?s=N4IgTCBcDaIAoEkDCBGAHAMQKwHYCKALAMwAESArgE4CWA9gM7UAuAniQHICGAdrSQCIBTAG6CANrQAOAW0HcmJAEK1OlACYgAugF8gA) | N/A | [Microchip documentation](https://www.microchip.com/en-us/product/PIC18F57Q43) | U2 |

**Estimated new-purchase cost:** $1.48

**Note:** Components already owned are listed at $0.00 additional cost. The resistor inventory follows the three 100 Ω resistors visible in the schematic (R1, R4, and R5), plus R2 and R3. Generic resistor and capacitor links lead to DigiKey component categories because the schematic specifies electrical values rather than exact manufacturer part numbers.

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


