# Component Selection

## Automatic Pet Food Dispenser — Optical Sensor Monitoring Subsystem

**Student:** Caleb Ross  

**Project:** Automatic Pet Food Dispenser  

**Subsystem:** Optical Sensor Monitoring and Fault Detection

## 1. Introduction

The purpose of the Optical Sensor Monitoring subsystem is to monitor movement of the dispensing mechanism and help identify potential faults in the Automatic Pet Food Dispenser. The subsystem interfaces with the PIC18F57Q43 Curiosity Nano microcontroller and the other parts of the dispenser. The major components considered in this report are a Vishay TCST1103 optical slot sensor, a Microchip MCP6004-I/P operational amplifier used for sensor signal conditioning, and a 5 V voltage regulator. The TCST1103 detects changes in an infrared beam when a slotted wheel or mechanical flag moves through the sensor. The sensor's phototransistor output is conditioned by the MCP6004-I/P circuit and is intended to be read by the PIC18F57Q43 through RA0/ADC1. The microcontroller can process these readings to help determine whether the dispensing mechanism is operating as expected. If a fault is detected, the subsystem is intended to request that the motor-driver subsystem stop the motor; the exact interface and fault-detection behavior must be confirmed during integration and firmware testing. The voltage regulator provides a regulated supply for compatible low-voltage circuitry. The microcontroller was preselected for the project and is excluded from the component comparison tables. Pushbuttons, resistors, capacitors, wires, and ordinary PCB materials are also excluded from the major-component comparison tables because they are supporting components rather than the primary components evaluated in this report.

## 2. Optical Slot Sensor Selection

**Subsystem: Position and Rotation Detection**

The optical slot sensor will detect movement of the dispensing mechanism in our Automatic Pet Food Dispenser. A rotating slotted wheel or mechanical flag will interrupt the infrared beam, allowing the system to monitor movement. The sensor output will be sent through the op-amp signal-conditioning circuit before reaching the PIC18F57Q43 Curiosity Nano.

### Table 1. Optical Slot Sensor Candidates

| Solution | Advantages | Disadvantages |
|---|---|---|
| **Option 1: Vishay TCST1103** — [DigiKey product page](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TCST1103/2354847) and [datasheet](https://www.vishay.com/en/product/83764/).<br><img src="https://caross10.github.io/caross10_EGR304_F26.github.io/02-Component-Selection/TCST1103.jpg" alt="TCST1103 optical slot sensor" width="150"> **Unit price:** approximately $1.48. **Slot width:** 3.1 mm. **Output:** phototransistor. | - 3.1 mm slot provides room for a small encoder wheel or mechanical flag.<br>- Through-hole package is easier to solder during prototyping and PCB assembly.<br>- Daylight-blocking filter helps reduce interference from ambient light.<br>- Lowest price among the three candidates.<br>- Phototransistor output can be used with an appropriate load resistor and signal-conditioning circuit. | - Requires an external current-limiting resistor for the infrared emitter.<br>- Phototransistor output requires a load/pull-up and signal-conditioning circuit.<br>- Sensor must be aligned with the moving mechanism.<br>- Mechanical flag or wheel must fit within the slot. |
| **Option 2: Vishay TCST2103** — [DigiKey product page](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TCST2103/2354849) and [datasheet](https://www.vishay.com/docs/81147/tcst2103.pdf).<br>**Unit price:** approximately $1.84. **Slot width:** 3.1 mm. **Output:** phototransistor. | - Supports optical interruption sensing in a suitable circuit.<br>- Through-hole mounting is suitable for student PCB assembly.<br>- 3.1 mm slot supports mechanical interruption sensing.<br>- Phototransistor output is suitable for detecting movement and rotation. | - Higher price than the TCST1103.<br>- Requires external emitter and output circuitry.<br>- Mechanical alignment is still required. |
| **Option 3: Omron EE-SX1103** — [DigiKey product page](https://www.digikey.com/en/products/detail/aratas-formerly-omron-components/EE-SX1103/355306) and [datasheet](https://omronfs.omron.com/en_US/ecb/products/pdf/en-ee_sx1103.pdf).<br>**Unit price:** approximately $1.75. **Slot width:** 2 mm. **Output:** phototransistor. | - Compact design can save PCB space.<br>- Through-hole mounting simplifies soldering.<br>- Narrow slot can support sensing with a thin mechanical flag. | - Narrower 2 mm slot requires more accurate mechanical alignment.<br>- Less clearance for a thicker rotating disk or flag.<br>- Requires external emitter and output circuitry. |

### Final Optical Slot Sensor Selection

**Choice: Vishay TCST1103.**

**Manufacturer:** Vishay Semiconductor

**Part number:** TCST1103

**Estimated unit cost:** $1.48

**Slot width:** 3.1 mm

**Output type:** Phototransistor

**Supplier:** DigiKey

The Vishay TCST1103 is the preferred optical slot sensor because it provides a good balance of performance, mechanical compatibility, ease of implementation, and cost. Its 3.1 mm sensing gap provides clearance for a thin slotted wheel or mechanical flag, while its through-hole package makes it practical to install and solder during prototyping. The sensor uses an infrared emitter and phototransistor, making it suitable for detecting interruptions caused by movement of the dispensing mechanism. Its daylight-blocking filter also helps reduce interference from surrounding light. The sensor requires an external current-limiting resistor for the infrared emitter and an appropriate load or pull-up circuit for the phototransistor. The conditioned sensor signal is intended to connect to the PIC18F57Q43 through RA0/ADC1. If the readings indicate an abnormal operating condition, the microcontroller is intended to request that the motor-driver subsystem stop the motor. The fault thresholds and stop-request interface must be confirmed during circuit integration and firmware testing. Compared with the other options, the TCST1103 offers similar sensing functionality at a lower unit price. Therefore, it is the preferred choice, provided the final mechanical design fits within its sensing gap.

## 3. Operational Amplifier Selection

The operational amplifier conditions the electrical signal from the TCST1103 optical slot sensor before it reaches the PIC18F57Q43 Curiosity Nano. The component must operate from the available supply voltage and provide input and output levels suitable for the intended signal. The candidates were compared based on supply-voltage compatibility, input/output voltage range, current consumption, package type, bandwidth, cost, and ease of assembly.

### Table 2. Operational Amplifier Candidates

| Solution | Advantages | Disadvantages |
|---|---|---|
| **Option 1: Microchip MCP6004-I/P** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060).<br><img src="https://caross10.github.io/caross10_EGR304_F26.github.io/02-Component-Selection/MCP6004.jpeg" alt="MCP6004 operational amplifier" width="150"> **Unit price:** approximately $0.59. **Stock:** 3,544 units listed in the retrieved listing. | - Operates from 1.8 V to 6 V, making it compatible with a 5 V supply.<br>- Provides rail-to-rail input and output operation.<br>- Contains four operational amplifiers in one package.<br>- Through-hole 14-pin package simplifies assembly.<br>- Low supply current makes it suitable for low-power signal conditioning. | - Four amplifier channels may be more than the subsystem requires.<br>- Approximately 1 MHz gain-bandwidth product limits high-frequency performance.<br>- Output current is limited by the device's electrical specifications.<br>- External feedback components are needed for amplifier configurations. |
| **Option 2: Texas Instruments LM358P** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM358P/277042).<br><img src="https://caross10.github.io/caross10_EGR304_F26.github.io/02-Component-Selection/LM358P.jpg" alt="LM358P operational amplifier" width="150"> **Unit price:** approximately $0.33. **Stock:** 25,138 units listed in the retrieved listing. | - Low unit cost.<br>- Two operational amplifiers in an 8-pin through-hole package.<br>- Suitable for many low-frequency amplifier and buffer circuits.<br>- Supports single-supply operation with a 5 V rail.<br>- Widely documented and straightforward to prototype. | - Input common-mode range does not extend fully to the positive supply rail.<br>- Output is not rail-to-rail.<br>- The available output range must be checked against the PIC ADC requirements.<br>- Its bandwidth and input/output limitations may restrict its suitability for some signal-conditioning configurations. |
| **Option 3: Texas Instruments LM324N** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM324N/277627).<br><img src="https://caross10.github.io/caross10_EGR304_F26.github.io/02-Component-Selection/LM324N.jpg" alt="LM324N operational amplifier" width="150"> **Unit price:** approximately $0.55. **Stock:** 51,889 units listed in the retrieved listing. | - Four operational amplifiers in a 14-pin through-hole package.<br>- Supports single-supply operation with a 5 V rail.<br>- Low unit cost.<br>- Can support several analog signal-conditioning stages.<br>- Through-hole construction is practical for prototyping. | - Output is not rail-to-rail.<br>- Input common-mode range does not extend fully to the positive supply rail.<br>- The output voltage may not reach the upper end of the ADC's input range.<br>- Four channels may be unnecessary if only one signal requires conditioning. |

### Final Operational Amplifier Selection

**Choice: Microchip MCP6004-I/P.**

**Manufacturer:** Microchip Technology

**Part number:** MCP6004-I/P

**Estimated unit cost:** $0.59

**Package:** 14-pin through-hole

**Supplier:** DigiKey

The Microchip MCP6004-I/P is the preferred operational amplifier because it operates from the planned 5 V supply and provides rail-to-rail input and output capability. These features make it suitable for conditioning the optical sensor signal before it reaches the PIC18F57Q43 through RA0/ADC1. Its low supply current is also beneficial for the dispenser's electronic system. Although the device contains four operational amplifiers, the additional channels provide flexibility if more signal-conditioning stages are needed later. The LM358P has a lower unit cost, but its input and output voltage limitations make it less suitable when the signal needs to use a broad portion of the 0–5 V range. The LM324N also provides four amplifier channels but does not offer rail-to-rail output operation. The sensor biasing, amplifier configuration, and expected output-voltage range must be verified during circuit design to ensure the signal remains within the PIC's permitted ADC input range. Because the MCP6004 is an operational amplifier rather than a dedicated comparator, its suitability for the required signal-processing behavior must also be verified using the manufacturer datasheet.

## 4. 5 V Voltage Regulator Selection

The voltage regulator provides a stable 5 V supply for compatible active electronics in the optical sensor monitoring subsystem. The regulator must supply the required load current while remaining within its electrical and thermal limits. The candidates were compared based on output voltage, rated current, package type, protection features, cost, and thermal considerations.

### Table 3. 5 V Voltage Regulator Candidates

| Solution | Advantages | Disadvantages |
|---|---|---|
| **Option 1: STMicroelectronics L7805CV** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964).<br><img src="https://caross10.github.io/caross10_EGR304_F26.github.io/02-Component-Selection/L7805CV.jpg" alt="L7805CV voltage regulator" width="150"> **Unit price:** approximately $1.08. **Stock:** 87,190 units listed in the retrieved listing. | - Provides a fixed regulated 5 V output.<br>- Nominal output-current capability of 1.5 A.<br>- Through-hole TO-220 package is practical for assembly and heat sinking.<br>- Includes overtemperature and short-circuit protection.<br>- Low unit cost and established manufacturer documentation. | - Linear regulation dissipates excess input power as heat.<br>- Requires sufficient input voltage above 5 V.<br>- A heatsink may be required at high load current or with a large input-to-output voltage difference.<br>- The rated current cannot be assumed to be continuously available under all thermal conditions. |
| **Option 2: onsemi MC7805CTG** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/onsemi/MC7805CTG/919333).<br><img src="https://caross10.github.io/caross10_EGR304_F26.github.io/02-Component-Selection/MC7805CTG.jpg" alt="MC7805CTG voltage regulator" width="150"> **Unit price:** approximately $0.99. **Stock:** 43,687 units listed in the retrieved listing. | - Provides a fixed 5 V output.<br>- Nominal output-current capability of 1 A.<br>- Through-hole TO-220 package is easy to assemble.<br>- Includes thermal shutdown and current-limiting protection.<br>- Lower unit cost than some alternative regulators. | - Its nominal 1 A output rating is lower than the 1.5 A rating of the L7805CV.<br>- Linear regulation produces heat as input voltage and output current increase.<br>- Requires sufficient input voltage above 5 V.<br>- Thermal performance must be checked before selecting the regulator for the complete load. |
| **Option 3: Texas Instruments LM340AT-5.0/NOPB** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM340AT-5-0-NOPB/148173).<br><img src="https://caross10.github.io/caross10_EGR304_F26.github.io/02-Component-Selection/LM340AT-5.0.jpg" alt="LM340AT-5.0 voltage regulator" width="150"> **Unit price:** approximately $1.97. **Stock:** 13,152 units listed in the retrieved listing. | - Provides a fixed regulated 5 V output.<br>- Nominal output-current capability of 1.5 A.<br>- Through-hole TO-220 package is suitable for assembly and heat sinking.<br>- Manufacturer documentation provides electrical and thermal specifications.<br>- Includes thermal and current protection features. | - Higher unit cost than the L7805CV.<br>- Linear-regulator power loss must be managed.<br>- Requires sufficient input voltage above 5 V.<br>- Full rated output current may require additional thermal management. |

### Final Voltage Regulator Selection

**Choice: STMicroelectronics L7805CV.**

**Manufacturer:** STMicroelectronics

**Part number:** L7805CV

**Estimated unit cost:** $1.08

**Output voltage:** 5 V

**Nominal output current:** 1.5 A

**Supplier:** DigiKey

The STMicroelectronics L7805CV is the preferred voltage regulator because it provides a fixed 5 V output, has a nominal output-current rating of 1.5 A, and uses a through-hole package that is practical for prototyping and assembly. It also offers thermal and short-circuit protection features. The MC7805CTG has a lower unit cost, but its nominal 1 A output-current rating provides less capacity if the final system load increases. The LM340AT-5.0/NOPB offers a similar nominal current rating but has a higher unit cost. Since the L7805CV is a linear regulator, its power dissipation and operating temperature must be evaluated using the actual input voltage and total load current. A suitable heatsink may be required, and the final design must confirm that the regulator can safely supply the connected circuitry.

## 5. Pin and Interface Table

The following table reflects the optical sensor monitoring subsystem connections shown in the Team 101 block diagram. Pin directions are described relative to the PIC18F57Q43 Curiosity Nano.

| Component or interface | PIC pin / signal | Direction relative to PIC | Signal type | Purpose |
|---|---|---|---|---|
| **Optical slot sensor - TCST1103** | Output to MCP6004-I/P | Analog signal to op-amp | Analog (0–5 V, 1 pin) | Detects changes in the optical sensor signal. |
| **Signal conditioning - MCP6004-I/P** | RA0 / ADC1 | Input | Analog (0–5 V, 1 pin) | Conditions the optical sensor signal before it reaches the PIC's ADC input. |
| **Debugging LED - 151051RS11000** | RD0 | Output | Digital (5 V, 1 pin) | Provides a visual indicator during testing and debugging. |
| **Debugging Button - B3F-4055** | RD1 | Input | Digital (5 V, 1 pin) | Provides a button input for testing and debugging. |
| **Status LED - 151051RS11000** | RD2 | Output | Digital (5 V, 1 pin) | Indicates a potential fault detected by the subsystem. |
| **Connector 1** | Pin 7 → RA1 | Input | Analog (0–5 V, 1 pin) | Interface to other subsystems. |
| **Power interface - LM7805CV** | +5 V | Supply | DC power | Supplies the regulated 5 V rail shown in the block diagram. |
| **Ground interface** | GND | Return | DC power return | Provides the common electrical reference for the connected circuitry. |

## 6. Final Component Selection Summary

| Major component | Selected candidate | Main reason for selection |
|---|---|---|
| **Optical slot sensor** | Vishay TCST1103 | 3.1 mm slot, through-hole package, suitable for detecting movement through interruption of an infrared beam, and favorable cost. |
| **Signal conditioning / Operational Amplifier** | Microchip MCP6004-I/P | Compatible with a 5 V supply and provides rail-to-rail input/output capability for conditioning the optical sensor signal. Its actual circuit behavior must be verified. |
| **5 V Voltage Regulator** | STMicroelectronics L7805CV | Fixed 5 V output, nominal 1.5 A capability, through-hole package, and favorable cost and availability. |

## 7. Conclusion

The component-selection process compared commercially available options for the major components in the Optical Sensor Monitoring subsystem. The candidates were evaluated based on electrical specifications, compatibility with the 5 V supply, package type, cost, and availability of manufacturer documentation. The Vishay TCST1103 is the preferred optical sensor because it provides a 3.1 mm slot, a phototransistor output, and a practical through-hole package at a favorable cost. The MCP6004-I/P is retained for sensor signal conditioning because it supports the planned 5 V supply and provides rail-to-rail input and output capability. The STMicroelectronics L7805CV remains the preferred regulator because it provides a fixed 5 V output and a nominal 1.5 A output-current rating in a through-hole package. The final implementation must verify the optical sensor's emitter resistor and phototransistor load, the op-amp circuit and signal range, the PIC ADC voltage limits, the regulator's thermal dissipation, and the total power consumption. The team must also confirm the interface and signal used to request a motor stop if a fault is detected. These checks are necessary to ensure that the selected components work together correctly in the Automatic Pet Food Dispenser.

## 8. References

The product pages below provide manufacturer information and datasheets for the components compared in this report. Reference prices and stock quantities are snapshots from the listings used during preparation and may change.

1. Vishay Semiconductor, [TCST1103 product page on DigiKey](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TCST1103/2354847).
2. Vishay Semiconductor, [TCST2103 product page and datasheet](https://www.digikey.com/en/products/detail/vishay-semiconductor-opto-division/TCST2103/2354849).
3. Omron, [EE-SX1103 product page and datasheet](https://www.digikey.com/en/products/detail/aratas-formerly-omron-components/EE-SX1103/355306).
4. Microchip Technology, [MCP6004-I/P product page and datasheet](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060).
5. Texas Instruments, [LM358P product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM358P/277042).
6. Texas Instruments, [LM324N product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM324N/277627).
7. STMicroelectronics, [L7805CV product page and datasheet](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964).
8. onsemi, [MC7805CTG product page and datasheet](https://www.digikey.com/en/products/detail/onsemi/MC7805CTG/919333).
9. Texas Instruments, [LM340AT-5.0/NOPB product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM340AT-5-0-NOPB/148173).
