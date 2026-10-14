title: Welcome
tags:

EGR304

Automatic Pet Food Dispenser

<center>
<font size="6">Caleb Ross — Engineering Datasheet</font><br>
EGR 304 — Embedded Systems Design<br>
<font size="8">Automatic Pet Food Dispenser</font><br>
Team 101
</center>

Introduction

This datasheet documents my individual engineering work for the Automatic Pet Food Dispenser project in EGR 304. The project involves designing an electronic system that can control the timing and operation of an automatic pet food dispenser. My work focuses on the electronic components, circuit design, microcontroller interfaces, and supporting documentation needed to develop and integrate the system.

This website serves as a central location for my design documents and component information. It will be updated as the project develops and design decisions are finalized.

Project Summary

The Automatic Pet Food Dispenser is designed to automate the process of dispensing pet food using electronic control and timing functions. The system requires hardware that can generate and process signals, interface with a microcontroller, and provide appropriate power to the electronic components.

The design uses the PIC18F57Q43 Curiosity Nano microcontroller as part of the control system. The electronic design work includes selecting components compatible with the system's power requirements, developing circuit documentation, and considering how the different hardware elements communicate with one another.

My individual work supports the larger team project by documenting the subsystem design, evaluating component options, and organizing the information needed to build, test, and improve the electronic system.

For additional information about the overall team project, see the team report.

My Contribution

My work focuses on the electronic design and documentation for the Automatic Pet Food Dispenser, with particular attention to the Timer/Scheduler subsystem and its interfaces with the rest of the system.

My engineering work includes:

Component selection: Comparing commercially available timer ICs, operational amplifiers, and voltage regulators based on electrical specifications, power requirements, package types, cost, and suitability for the design.

Timer and signal conditioning: Evaluating the TLC555CP timer and MCP6004-I/P operational amplifier for timing and signal-conditioning functions, including the need to verify the final signal behavior against the circuit requirements.

Power regulation: Evaluating 5 V linear regulators, including the L7805CV, and considering current requirements and thermal dissipation.

Microcontroller integration: Working with the PIC18F57Q43 Curiosity Nano board and its digital I/O, ADC, UART, and PWM functionality in embedded-systems laboratory work.

Circuit and PCB design: Developing schematics, creating custom KiCad symbols and footprints, checking electrical and design-rule errors, and preparing PCB manufacturing files.

Engineering documentation: Maintaining design diagrams, component comparisons, pin/interface information, and power-budget documentation to support implementation and future revisions.

The following pages provide access to the main design documents for this project.

Design Documentation

Block Diagram — Overview of the system structure, major functional blocks, and subsystem interfaces.

Component Selection — Comparison of component alternatives, their advantages and disadvantages, and the rationale for the selected timer, operational amplifier, and voltage regulator.

Power Budget — Documentation for evaluating the electrical power requirements of the subsystem and its components.

Bill of Materials (BOM) — Reference for the components and materials used in the design.

Design Approach

The design process involves evaluating component specifications, checking compatibility between circuit elements, and documenting the reasoning behind hardware decisions. Component choices must account for supply voltage, current consumption, signal levels, timing behavior, physical package requirements, and thermal limitations.

As the project progresses, the design documentation will be refined to reflect the actual circuit implementation, test results, and any changes made during integration. The goal is to maintain an accurate and useful reference for understanding the subsystem and how it contributes to the operation of the Automatic Pet Food Dispenser.
