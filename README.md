# The Smart Extension Cord 💡🔌

**Project Report**
Department of Electronic & Telecommunication Engineering,
University of Moratuwa, Sri Lanka.
EN1190 Engineering Design Project - August 2024

## 🚀 Project Overview

Many households struggle with a lack of visibility into the power consumption of individual devices, making it difficult to optimize energy usage. Traditional power strips lack remote control, leading to inconvenience and energy wastage. This project, "The Smart Extension Cord," aims to address these limitations by providing a comprehensive solution for efficient energy management. ✨

Our smart extension cord system integrates power consumption monitoring and the ability to control multiple outlets remotely via a smartphone app 📱. This provides a holistic approach to managing energy usage efficiently and conveniently, promoting energy savings 💰 and offering a user-friendly experience.

## 🌟 Key Features

*   ✅ **Remote On/Off Functionality:** Control individual outlets remotely.
*   📊 **Power Consumption Monitoring:** Track energy usage of connected devices.
*   🔗 **Multiple Outlets:** Manage several devices simultaneously.
*   🤳 **Smartphone App Control:** Intuitive mobile application for monitoring and control.

## 🤔 Justification for Selection

A survey (70 responses) revealed that 81.4% of individuals had not encountered a product monitoring power consumption of various devices. Key reasons for interest in a smart extension cord include:
*   Energy Savings (80%) 🌿
*   Convenience (65.7%) 👍
*   Security (27.1%) 🛡️

<p align="center">
  <img src="pictures/analysis.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 1: Analysis of user interest drivers.
</p>


**

## 🏗️ System Architecture

The system architecture is designed for robust performance and ease of use.

<p align="center">
  <img src="pictures/blockdiagram.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 2: System Block Diagram.
</p>



## 🛠️ Technology Stack

### Key Hardware Components 🔩
*   ESP32-WROOM-32 Microcontroller
*   ACS712 ICs (Current Sensors)
*   ZMPT101B Voltage Sensor
*   5V Power Supply
*   5V Relays

### Software & Tools 💻
*   **PCB Design & Simulation:** Proteus, Altium Designer, LTspice
*   **Smartphone Application:** MIT App Inventor, Firebase
*   **Enclosure Design:** SolidWorks

## 🎨 Product Design & Enclosure

### Initial Sketches ✍️
The enclosure was designed for functionality, safety, and aesthetics.

<p align="center">
  <img src="pictures/upperpart.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 3: Initial Sketch of the Top Enclosure Part.
</p>


<p align="center">
  <img src="pictures/middlepartt.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 4: Initial Sketch of the middle Enclosure Part.
</p>

<p align="center">
  <img src="pictures/lowerpartt.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 5: Initial Sketch of the Lower Enclosure Part.
</p>





### Final CAD Design (SolidWorks) 🧊
Finalized designs were created for 3D printing.

<p align="center">
  <img src="pictures/toppart.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 6: Final CAD Model of the Upper Enclosure Part.
</p>



<p align="center">
  <img src="pictures/middlepart.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 7: Final CAD Model of the Middle Enclosure Part.
</p>

<p align="center">
  <img src="pictures/lowerpart.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 8: Final CAD Model of the Lower Enclosure Part.
</p>


## 🔬 PCB Design

### Schematics 📝
Detailed schematics were designed for the system's electronics.

<p align="center">
  <img src="pictures/sheet1.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 9: Schematic Sheet 1 - Microcontroller and Power Management.
</p>


<p align="center">
  <img src="pictures/sheet2.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 10: Schematic Sheet 2 - Relay and Current Sensor for an Outlet.
</p>



<p align="center">
  <img src="pictures/sheet3.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 11: Schematic Sheet 3 - Master Relay for Overall Power Control.
</p>




### PCB Layout 🖼️
The PCB was designed using Altium Designer.

**2D Layout Mode**
<p align="center">
  <img src="pictures/2d.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 12: 2D PCB Layout.
</p>




**2D Layout Mode with Multi-Layer View**
<p align="center">
  <img src="pictures/multilayer.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 13: 2D PCB Layout with Multi-Layer View.
</p>


**3D Layout Mode**
<p align="center">
  <img src="pictures/3d.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 14: 3D Rendered PCB Layout.
</p>


## ✨ Final Product 🎉

The assembled Smart Extension Cord, focusing on durability, safety, and aesthetics using fire-resistant materials.

<p align="center">
  <img src="pictures/top.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 15: Top View of the Assembled Smart Extension Cord.
</p>



<p align="center">
  <img src="pictures/side.png" width="500" alt=""/>
</p>

<p align="center">
  Figure 16: Side View of the Assembled Smart Extension Cord.
</p>



---

This README provides a comprehensive overview of "The Smart Extension Cord" project, its design, and implementation.
