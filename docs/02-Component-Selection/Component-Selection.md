# Individual Component Selection

## Automatic Pet Food Dispenser — Timer/Scheduler Subsystem

**Student:** Caleb Ross  

**Project:** Automatic Pet Food Dispenser  

**Subsystem:** Timer/Scheduler

## 1. Introduction

The purpose of the Timer/Scheduler subsystem is to generate and condition timing signals for the Automatic Pet Food Dispenser. The subsystem interfaces with the PIC18F57Q43 Curiosity Nano microcontroller and other parts of the dispenser to support the timing and control functions required by the design.

The major components considered in this report are a clock/timer integrated circuit, an MCP6004-I/P operational amplifier used in the comparator stage, and a 5 V voltage regulator. In the block diagram, the timer provides an analog 0–5 V signal to the comparator stage, which produces a digital 5 V signal for the PIC18F57Q43. The voltage regulator provides a regulated supply for the subsystem.

The microcontroller was preselected for the project and is excluded from the component comparison tables. Pushbuttons, resistors, capacitors, wires, and ordinary PCB materials are also excluded because they are not considered major components under the assignment requirements.

## 2. Clock/Timer Selection

The clock/timer generates the timing waveform used by the Timer/Scheduler subsystem. The candidates were compared based on supply voltage, power consumption, timing flexibility, operating frequency, package type, and ease of implementation.

### Table 1. Clock/Timer Candidates

| Solution | Advantages | Disadvantages |
|---|---|---|
| **Option 1: Texas Instruments LM555CN/NOPB** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM555CN-NOPB/6575). **Unit price:** approximately $1.44. **Stock:** 14,800 units listed in the retrieved listing. | - The 8-pin through-hole package is easy to use for breadboard prototyping and PCB assembly.<br>- Operates from 4.5 V to 16 V, making it compatible with a 5 V supply.<br>- Supports monostable and astable configurations for one-shot timing or repeating oscillation.<br>- Widely documented and suitable for basic timing applications. | - Typical supply current is higher than that of CMOS timer alternatives.<br>- The minimum operating voltage is 4.5 V.<br>- Timing accuracy depends on external resistor and capacitor tolerances.<br>- Does not independently maintain the time of day or generate a precision analog ramp without additional circuitry. |
| **Option 2: Texas Instruments TLC555CP** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/TLC555CP/277502). **Unit price:** approximately $1.40. **Stock:** 13,095 units listed in the retrieved listing. | - Operates from 2 V to 15 V and is compatible with the 5 V supply.<br>- CMOS design provides substantially lower supply current than a conventional bipolar 555 timer.<br>- Through-hole 8-pin package simplifies prototyping and assembly.<br>- Supports monostable and astable operation.<br>- Suitable for low-power timing circuits. | - Requires external timing components.<br>- Timing accuracy depends on the resistor, capacitor, and operating conditions.<br>- A digital output does not directly provide a linear analog ramp.<br>- Costs slightly more than some basic bipolar timer alternatives. |
| **Option 3: Texas Instruments NE555P** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/NE555P/277057). **Unit price:** approximately $0.59. **Stock:** 50,761 units listed in the retrieved listing. | - Lower unit cost than the other candidates.<br>- Through-hole 8-pin package is convenient for prototyping and soldering.<br>- Supports monostable and astable timing configurations.<br>- Operates from a supply voltage compatible with a 5 V system.<br>- Has manufacturer documentation and is widely used in basic timing circuits. | - Higher supply-current consumption than CMOS timer alternatives.<br>- Timing accuracy depends on external resistor and capacitor tolerances.<br>- The timing interval is affected by the selected external components.<br>- Does not independently maintain the time of day or provide a precision analog ramp without additional circuitry. |

### Final Clock/Timer Selection

**Choice: Texas Instruments TLC555CP.**

The TLC555CP is the preferred candidate because it provides the timing functions needed for the subsystem while consuming less supply current than conventional bipolar 555 timer alternatives. Its 2 V to 15 V operating range makes it compatible with the planned 5 V supply, and its through-hole package simplifies assembly and prototyping.

The LM555CN/NOPB is another suitable candidate, but its higher supply-current consumption makes it less attractive for a low-power embedded system. The NE555P has the lowest unit cost of the three candidates and is a reasonable alternative when minimizing component cost is the main priority.

The final timing resistor and capacitor values must be selected according to the required interval. The output waveform must also be verified against the signal-conditioning stage. A 555 timer produces a timing waveform, and its timing-capacitor voltage normally changes between internal threshold levels; it does not automatically produce a linear 0–5 V analog ramp.

## 3. Operational Amplifier Selection

The MCP6004-I/P is shown in the comparator stage of the block diagram. It receives the timer’s analog signal and produces a digital output for the PIC18F57Q43. The component must operate from the available supply voltage and provide input and output levels suitable for the intended signal.

The candidates were compared based on supply-voltage compatibility, input/output voltage range, current consumption, package type, bandwidth, cost, and ease of assembly.

### Table 2. Operational Amplifier Candidates

| Solution | Advantages | Disadvantages |
|---|---|---|
| **Option 1: Microchip MCP6004-I/P** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060). **Unit price:** approximately $0.59. **Stock:** 3,544 units listed in the retrieved listing. | - Operates from 1.8 V to 6 V, making it compatible with a 5 V supply.<br>- Provides rail-to-rail input and output operation.<br>- Contains four operational amplifiers in one package.<br>- Through-hole 14-pin package simplifies assembly.<br>- Low supply current makes it suitable for low-power signal conditioning. | - Four amplifier channels may be more than the subsystem requires.<br>- Approximately 1 MHz gain-bandwidth product limits high-frequency performance.<br>- Output current is limited by the device's electrical specifications.<br>- External feedback components are needed for amplifier configurations. |
| **Option 2: Texas Instruments LM358P** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM358P/277042). **Unit price:** approximately $0.33. **Stock:** 25,138 units listed in the retrieved listing. | - Low unit cost.<br>- Two operational amplifiers in an 8-pin through-hole package.<br>- Suitable for many low-frequency amplifier and buffer circuits.<br>- Supports single-supply operation with a 5 V rail.<br>- Widely documented and straightforward to prototype. | - Input common-mode range does not extend fully to the positive supply rail.<br>- Output is not rail-to-rail.<br>- The available output range must be checked against the PIC ADC requirements.<br>- Its bandwidth and input/output limitations may restrict its suitability for some signal-conditioning configurations. |
| **Option 3: Texas Instruments LM324N** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM324N/277627). **Unit price:** approximately $0.55. **Stock:** 51,889 units listed in the retrieved listing. | - Four operational amplifiers in a 14-pin through-hole package.<br>- Supports single-supply operation with a 5 V rail.<br>- Low unit cost.<br>- Can support several analog signal-conditioning stages.<br>- Through-hole construction is practical for prototyping. | - Output is not rail-to-rail.<br>- Input common-mode range does not extend fully to the positive supply rail.<br>- The output voltage may not reach the upper end of the ADC's input range.<br>- Four channels may be unnecessary if only one signal requires conditioning. |

### Final Operational Amplifier Selection

**Choice: Microchip MCP6004-I/P.**

The MCP6004-I/P is the preferred candidate because it operates from the planned 5 V supply and provides rail-to-rail input and output capability. These features are useful in the comparator stage shown in the block diagram, where the analog timer signal is converted into a digital signal for the PIC. Its behavior when used as a comparator must still be verified against the manufacturer datasheet.

Its low supply current is also beneficial for an embedded system. Although the device contains four amplifiers, the additional channels provide flexibility if more signal-conditioning stages are needed later.

The LM358P has a lower unit cost, but its input and output limitations make it less suitable when the signal must use most of the 0–5 V range. The LM324N offers four amplifier channels but does not provide rail-to-rail output operation.

The comparator threshold and input signal range must be confirmed during circuit design. The output must satisfy the PIC digital-input voltage specifications. The MCP6004 is an operational amplifier rather than a dedicated comparator, so its suitability for the switching behavior required by this block must be verified using its datasheet.

## 4. 5 V Voltage Regulator Selection

The voltage regulator provides a stable 5 V supply for the subsystem's active electronics. The regulator must supply the required load current while remaining within its electrical and thermal limits.

The candidates were compared based on output voltage, rated current, package type, protection features, cost, and thermal considerations.

### Table 3. 5 V Voltage Regulator Candidates

| Solution | Advantages | Disadvantages |
|---|---|---|
| **Option 1: STMicroelectronics L7805CV** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964). **Unit price:** approximately $1.08. **Stock:** 87,190 units listed in the retrieved listing. | - Provides a fixed regulated 5 V output.<br>- Nominal output-current capability of 1.5 A.<br>- Through-hole TO-220 package is practical for assembly and heat sinking.<br>- Includes overtemperature and short-circuit protection.<br>- Low unit cost and established manufacturer documentation. | - Linear regulation dissipates excess input power as heat.<br>- Requires sufficient input voltage above 5 V.<br>- A heatsink may be required at high load current or with a large input-to-output voltage difference.<br>- The rated current cannot be assumed to be continuously available under all thermal conditions. |
| **Option 2: onsemi MC7805CTG** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/onsemi/MC7805CTG/919333). **Unit price:** approximately $0.99. **Stock:** 43,687 units listed in the retrieved listing. | - Provides a fixed 5 V output.<br>- Nominal output-current capability of 1 A.<br>- Through-hole TO-220 package is easy to assemble.<br>- Includes thermal shutdown and current-limiting protection.<br>- Lower unit cost than some alternative regulators. | - Its nominal 1 A output rating is lower than the 1.5 A rating of the L7805CV.<br>- Linear regulation produces heat as input voltage and output current increase.<br>- Requires sufficient input voltage above 5 V.<br>- Thermal performance must be checked before selecting the regulator for the complete load. |
| **Option 3: Texas Instruments LM340AT-5.0/NOPB** — [DigiKey product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM340AT-5-0-NOPB/148173). **Unit price:** approximately $1.97. **Stock:** 13,152 units listed in the retrieved listing. | - Provides a fixed regulated 5 V output.<br>- Nominal output-current capability of 1.5 A.<br>- Through-hole TO-220 package is suitable for assembly and heat sinking.<br>- Manufacturer documentation provides electrical and thermal specifications.<br>- Includes thermal and current protection features. | - Higher unit cost than the L7805CV.<br>- Linear-regulator power loss must be managed.<br>- Requires sufficient input voltage above 5 V.<br>- Full rated output current may require additional thermal management. |

### Final Voltage Regulator Selection

**Choice: STMicroelectronics L7805CV.**

The L7805CV is the preferred candidate because it provides a fixed 5 V output, has a nominal 1.5 A output-current rating, uses a through-hole package, and has a lower unit price than the LM340AT-5.0/NOPB.

The MC7805CTG has a lower unit cost, but its nominal 1 A current rating provides less capacity if the subsystem's final current requirement increases. The LM340AT-5.0/NOPB provides a similar nominal current rating to the L7805CV but has a higher unit cost.

The regulator must be checked against the total system load and the external supply voltage. Its power dissipation can be estimated using

$$

P_{loss}=(V_{in}-V_{out})I\_{out}

$$

For example, if the input voltage is 9 V, the output voltage is 5 V, and the load current is 0.5 A,

$$

P_{loss}=(9-5)(0.5)=2.0\text{ W}

$$

This amount of heat may require a heatsink or a different input-supply arrangement. The external source, regulator, and load must therefore be evaluated together.

## 5. Pin and Interface Table

The following table follows the Timer/Scheduler block diagram. Pin directions are described relative to the PIC18F57Q43. Where the diagram does not show a specific physical pin assignment, the table does not invent one.

| Component or interface | PIC pin / signal | Direction relative to PIC | Signal type | Purpose |
|---|---|---|---|---|
| Clock/Timer — TLC555 | ADC1 / RA0 | Input | Analog, 0–5 V as shown in the block diagram | Receives the timer's analog timing signal for measurement by the PIC ADC. |
| Comparator — MCP6004 | ADC2 / RA1, as drawn | Input | Digital, nominal 5 V as shown in the block diagram | Receives the comparator's digital output after the analog timing signal is compared against a threshold. |
| **Button 1 — Aratas B3F-4055** | **RA1 / Digital I/O** | Input | Digital | Detects a user button press through the PIC's RA1 digital I/O pin. |
| PWM interface | RA2 / PWM | Output | Digital/PWM | Provides a pulse-width-modulated output if required by the final implementation. |
| Digital I/O interface | RA1, RB2, RC4, RD0, RD1 | Input/output, depending on signal | Digital | Provides the digital I/O signals identified in the block diagram for subsystem control and communication. |
| **Connector 1** | **RD0 / Digital I/O** | Input/output, depending on the exchanged signal | Digital | Connects the Timer/Scheduler subsystem to the other subsystem through the PIC's RD0 digital I/O connection. The connector layout shows eight positions, with pins 1–4 designated for digital signals and pins 5–8 designated for analog signals. |
| **Connector 2** | External subsystem interface; individual PIC pin assignments must follow the finalized wiring | Input/output, depending on exchanged signals | Digital and analog connector groups | Provides the additional subsystem interface shown in the block diagram. The connector layout identifies pins 1–4 as digital and pins 5–8 as analog. |
| Power interface | +5 V | Supply | DC power | Supplies the regulated logic rail to the subsystem. |
| Ground interface | GND | Return | DC power return | Provides the common electrical reference for the circuit. |

**Important pin-assignment note:** The block diagram appears to assign **RA1 to both the comparator output (ADC2) and Button 1**. These are separate signals, so the final schematic must resolve this conflict before the circuit is built. They cannot independently use the same physical pin at the same time without an appropriate design change. The table records the assignments as shown rather than silently changing them. Connector 1 is connected to RD0 as shown in the diagram. The exact individual analog connector pin assignments and the complete Connector 2 pin mapping should follow the finalized subsystem wiring.

## 6. Final Component Selection Summary

| Major component | Selected candidate | Main reason for selection |
|---|---|---|
| **Clock/Timer** | Texas Instruments TLC555CP | Low supply current, 5 V compatibility, through-hole package, and adequate timing capability. |
| **Comparator stage / Operational Amplifier** | Microchip MCP6004-I/P | Rail-to-rail input/output operation, low-voltage compatibility, and low supply current. |
| **5 V Voltage Regulator** | STMicroelectronics L7805CV | Fixed 5 V output, nominal 1.5 A capability, through-hole package, and favorable cost and availability. |

## 7. Conclusion

The component-selection process compared three commercially available solutions for each major component category. The candidates were evaluated based on electrical specifications, compatibility with the 5 V supply, current consumption, package type, cost, and availability of manufacturer documentation.

The TLC555CP is the preferred timer because it offers low supply-current consumption and flexible timing configurations. The MCP6004-I/P is the preferred component for the comparator stage because its rail-to-rail input and output capability is useful for converting the timer signal into a digital signal for the PIC, subject to verification of its suitability for comparator operation. The L7805CV is the preferred regulator because it provides a fixed 5 V output and a nominal 1.5 A output-current rating in a practical through-hole package.

The final implementation must verify the required timing interval, signal waveform, comparator threshold and switching behavior, regulator thermal dissipation, and total power consumption. These checks are necessary to ensure that the selected components work together correctly and meet the electrical requirements of the Automatic Pet Food Dispenser.


## 8. References

The product pages below provide manufacturer information and datasheets for the components compared in this report. Reference prices and stock quantities are snapshots from the listings used during preparation and may change.

1. Texas Instruments, [LM555CN/NOPB product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM555CN-NOPB/6575).
2. Texas Instruments, [TLC555CP product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/TLC555CP/277502).
3. Texas Instruments, [NE555P product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/NE555P/277057).
4. Microchip Technology, [MCP6004-I/P product page and datasheet](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060).
5. Texas Instruments, [LM358P product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM358P/277042).
6. Texas Instruments, [LM324N product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM324N/277627).
7. STMicroelectronics, [L7805CV product page and datasheet](https://www.digikey.com/en/products/detail/stmicroelectronics/L7805CV/585964).
8. onsemi, [MC7805CTG product page and datasheet](https://www.digikey.com/en/products/detail/onsemi/MC7805CTG/919333).
9. Texas Instruments, [LM340AT-5.0/NOPB product page and datasheet](https://www.digikey.com/en/products/detail/texas-instruments/LM340AT-5-0-NOPB/148173).
