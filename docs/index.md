title: Welcome
tags:

EGR304

Automatic Pet Food Dispenser

<center>
<font size="6">Caleb Ross Datasheet</font><br>
as part of<br>
<font size="8">Automatic Pet Food Dispenser</font><br>
for<br>
<font size="5">Team 101</font>
</center>

Introduction

This datasheet documents my individual engineering work for the Automatic Pet Food Dispenser project in EGR 304. It organizes the design information, component selections, and supporting documentation for the electronic system.

Project Summary

The Automatic Pet Food Dispenser is designed to automate pet food dispensing using electronic timing and control. The system uses electronic components and a microcontroller to support the timing, signal processing, and control functions needed for operation.

My work focuses on the Timer/Scheduler subsystem, including component selection, power requirements, signal conditioning, and interfaces with the PIC18F57Q43 Curiosity Nano microcontroller.

For additional information about the overall project, see the team report.

My Contribution

My contributions focus on the electronic design and documentation for the Automatic Pet Food Dispenser, including:

Component selection: Comparing timer ICs, operational amplifiers, and voltage regulators based on electrical specifications, cost, package type, and compatibility with the planned 5 V supply.

Timer and signal conditioning: Evaluating the TLC555CP timer and MCP6004-I/P operational amplifier for the Timer/Scheduler subsystem.

Power regulation: Evaluating 5 V regulators, including the L7805CV, and considering current requirements and heat dissipation.

Microcontroller development: Working with the PIC18F57Q43 Curiosity Nano and its ADC, UART, PWM, and digital I/O functionality in laboratory exercises.

Circuit and PCB design: Creating and checking schematics, developing custom KiCad symbols and footprints, resolving design-rule issues, and preparing Gerber files.

Engineering documentation: Maintaining design diagrams, component comparisons, interface information, and power budget documentation.

Design Documentation

Block Diagram — Shows the system's main functional blocks and connections.

Component Selection — Compares component alternatives and explains the selected timer, operational amplifier, and voltage regulator.

Power Budget — Provides documentation for the subsystem's power requirements.

Bill of Materials (BOM) — Provides a reference for the components and materials used in the design.

Design Approach

Component decisions must account for supply voltage, current consumption, signal levels, timing behavior, package requirements, and thermal limitations. This datasheet will be updated as the circuit is developed, tested, and integrated with the rest of the dispenser.

The goal is to maintain an accurate record of the subsystem's design decisions and provide documentation that helps the team understand, implement, and improve the electronic system.
