# Smart Extension Cord

> **Authors:**  
> - Sadaruwan I.J.M.J (220542J)  
> - Pahasara L.P.P (220439B)  
> - Budvin M.P.L (220077L)  
> - Perera M.D.R.N (220468L)  
>
> **Course:** EN1190 Engineering Design Project  
> **Institution:** Department of Electronic & Telecommunication Engineering, University of Moratuwa, Sri Lanka  
> **Date:** August 2024  

---

## Table of Contents

1. [Overview](#overview)  
2. [Problem Specification](#problem-specification)  
   - [Arriving at a Problem](#arriving-at-a-problem)  
   - [Our Solution](#our-solution)  
   - [Justification for Selection](#justification-for-selection)  
3. [Feasibility Analysis](#feasibility-analysis)  
   - [Technical Feasibility](#technical-feasibility)  
     - [Hardware Feasibility](#hardware-feasibility)  
     - [Software Feasibility](#software-feasibility)  
   - [Economic Feasibility](#economic-feasibility)  
4. [Product Architecture](#product-architecture)  
5. [Key Hardware Components](#key-hardware-components)  
6. [Product Enclosure](#product-enclosure)  
   - [Initial Sketches](#initial-sketches)  
   - [Final Sketches](#final-sketches)  
7. [PCB Design](#pcb-design)  
   - [Schematics](#schematics)  
   - [PCB Layout](#pcb-layout)  
8. [Final Product Photos](#final-product-photos)  
9. [Marketing, Sales, and After-Sale Considerations](#marketing-sales-and-after-sale-considerations)  
   - [Marketing](#marketing)  
   - [Sales](#sales)  
   - [After-Sales Considerations](#after-sales-considerations)  
10. [Task Allocation](#task-allocation)  
11. [Project Budget](#project-budget)  

---

## Overview

The **Smart Extension Cord** is a next-generation power strip designed to give users real-time visibility into the energy consumption of each connected device, along with remote on/off control via a smartphone application. Traditional power strips lack granular monitoring and convenience. By integrating IoT features, energy-measurement ICs, and Wi-Fi connectivity, our system provides:

- **Real-time power consumption monitoring** (per outlet)  
- **Remote on/off switching** of individual outlets through a mobile app  
- **Multiple outlets** (up to 4 channels) to control and monitor several devices simultaneously  
- **Intuitive smartphone interface** for easy management from anywhere in the world  

All hardware is housed in a fire-resistant, aesthetically pleasing enclosure. The firmware on the onboard microcontroller aggregates sensor data (voltage & current), computes power usage, and communicates with a cloud server via Wi-Fi. The smartphone app (built using MIT App Inventor & Firebase) retrieves data and sends commands back to the device.

---

## Problem Specification

### Arriving at a Problem

Many households struggle with a lack of visibility into the power consumption of individual devices. Standard power strips require manual toggling and provide zero feedback on which appliances draw the most energy. Even existing “smart plugs” on the market often:

- Report inaccurate power readings  
- Support only a single outlet, making multi-device monitoring cumbersome  
- Lack a holistic ecosystem for both measurement and convenient remote control  

As a result:

> > *Users cannot identify energy-intensive appliances, cannot optimize energy usage effectively, and must physically interact with each switch to toggle devices, leading to inconvenience and potential energy waste.*  

### Our Solution

To address these limitations, we designed and implemented a **Smart Extension Cord** that offers:

1. **Remote On/Off Functionality**  
   - Each of the four outlets can be switched on or off independently via a smartphone app.  
2. **Power Consumption Monitoring**  
   - Built-in voltage and current sensing (using ACS712 and ZMPT101B) to measure real-time power draw per outlet.  
3. **Multiple Outlets**  
   - Four individually controllable AC outlets, powered by 5V relays.  
4. **Smartphone App Control**  
   - Wi-Fi connectivity (ESP32) links the device to a cloud database (Firebase).  
   - The mobile app (MIT App Inventor) displays live energy data and lets users toggle outlets with a single tap.  

Collectively, these subsystems form a unified solution for convenience and energy savings. Users can now:

- Track exactly how much power each device is consuming (in Watts).  
- Turn devices on/off remotely (e.g., switch off a heater from work).  
- Schedule automated tasks (in future versions).  

### Justification for Selection

We conducted a survey of **70 respondents** to understand consumer pain points. Key findings:

- **81.4%** had never used a product that monitored multiple outlets’ consumption.  
- Among those who had seen similar devices, many cited **inaccurate readings**, **limited compatibility**, and **unreliable remote control** as major drawbacks.  

Based on user feedback, the most desired features were:

1. **Ease of use** (simple UI, one-touch control)  
2. **Accurate power measurement**  
3. **Robust remote control (low latency, secure)**  

The analysis of survey results is summarized in Figure 1 below.

![Figure 1: Survey Analysis Chart](pictures/.analysis.png)

*Figure Explanation:*  
- The pie chart (Figure 1) shows that over 80% of respondents have never encountered a reliable multi-outlet power monitoring solution.  
- Of those who did, main complaints centered around inaccuracy and poor remote responsiveness.

We incorporated these insights to focus development on reliable sensor calibration, a user-friendly app, and secure Wi-Fi communication.

---

## Feasibility Analysis

### Technical Feasibility

#### Hardware Feasibility

All major components are **off-the-shelf** and readily available:

- **ESP32-WROOM-32** (MCU + Wi-Fi)  
- **ACS712 Hall-effect current sensors** (one per outlet)  
- **ZMPT101B Voltage sensor** (common voltage sensing input)  
- **5V Relays** (to switch each AC outlet)  
- **Power supply module** (5V regulator for MCU and sensors)  

By choosing modules with well-known footprints, we ensured a compact PCB design that fits within our 3D-printed enclosure. The components have been prototyped on breadboards (Proteus, LTspice) to validate functionality before committing to PCB fabrication in Altium.

#### Software Feasibility

1. **Firmware (ESP32):**  
   - Written in Arduino/C++ using the ESP-IDF environment.  
   - Handles:
     - ADC sampling of ACS712 and ZMPT101B (with appropriate filtering).  
     - Power calculation (Volts × Amps → Watts).  
     - Wi-Fi connectivity, Secure TCP/IP communication with Firebase.  
     - Relay control logic (GPIO toggles).  
   - OTA update capacity considered for future revisions.

2. **Mobile App:**  
   - Developed using **MIT App Inventor** to quickly prototype the UI.  
   - Integrates with **Firebase Realtime Database** for:
     - Uploading live power data from ESP32.  
     - Storing user commands (on/off) that the ESP32 polls/receives.  
   - Basic authentication flows (email/password) using Firebase Authentication.

3. **PCBs & Simulation:**  
   - **Proteus** and **LTspice** used for initial sensor and relay switching simulations.  
   - **Altium Designer** for schematic capture and PCB layout (multi-layer).

All software tools chosen are industry standard, open to students, and match our team’s skill level.

### Economic Feasibility

A detailed **bill of materials (BOM)** yielded a per-unit cost of approximately **LKR 3,500** (including sensors, MCU, relays, PCB fabrication, and enclosure materials). We project:

- **Retail Price:** ~LKR 5,000 per unit (competitive with single-outlet smart plugs).  
- **Target Market:** Homeowners, small businesses interested in energy savings.  
- **Break-even Point:** ~400 units sold (given initial R&D and tooling costs).  

Long-term, the device’s ability to **reduce unnecessary energy draw** (e.g., phantom loads) can lead customers to recoup their investment in under 6 months (depending on local electricity rates).  

---

## Product Architecture

Below is the block diagram illustrating how various submodules interact:

```text
                     ┌────────────────────┐
    230–240VAC, 50Hz │    Power Input     │
                     └────────────────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │    Power Supply     │
                    │     (5V Regulator)  │
                    └─────────────────────┘
                               │
                               ▼
┌───────────────┐    ┌─────────────────────┐    ┌─────────────────────┐
│  ACS712 Current◀───┤ ESP32-WROOM-32 MCU  │───▶│  Wi-Fi / Firebase   │
│   Sensors (×4) │    │   & Control Logic   │    │ (Cloud & App Sync)  │
└───────────────┘    └─────────────────────┘    └─────────────────────┘
         │                    ▲    ▲    ▲
         │                    │    │    │
         ▼                    │    │    │
┌─────────────────┐           │    │    │
│ ZMPT101B Voltage│───────────┘    │    │
│     Sensor      │                │    │
└─────────────────┘                │    │
         │                         │    │
         ▼                         │    │
    ┌──────────┐                    │    │
    │  Relays  │◀───────────────────┘    │
    │ (×4)     │                         │
    └──────────┘                         │
         │                               │
         ▼                               │
    ┌───────────┐                        │
    │ AC Outlets│◀───────────────────────┘
    └───────────┘
