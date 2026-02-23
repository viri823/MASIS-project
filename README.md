# MASIS-project
MASIS *(Modular, Automatic, Smart Irrigation System)* is a modular IoT-based smart irrigation system designed for real-time soil monitoring and automated plant watering. The system was built around a distributed architecture using dual ESP32-based custom PCBs, long-range LoRa communication, MQTT cloud integration, and a Node-RED dashboard interface.

The project achieved **1st place in an Embedded Systems competition**, demonstrating full-stack integration of hardware, firmware, communication protocols, and IoT infrastructure.
# Project Overview
MASIS was designed to provide:
- Real-time soil moisture monitoring
- Intelligent automated irrigation
- Remote supervision and manual override
- Scalable architecture for future expansion

The system separates sensing, control logic, power electronics, and cloud communication into dedicated layers, ensuring modularity and robustness.
# System Architecture
The architecture is divided into two main hardware modules:
1. Monitoring Board (Sensor Node)
   - Microcontroller: ESP32
   - Soil moisture sensors
   - LoRa communication module
   - Real-time data acquisition
   - Low-power logic stage

The monitoring board is responsible exclusively for acquiring soil moisture data and transmitting it via LoRa to the control board.\\

2. Control Board (Gateway & Actuation Node)
   - Microcontroller: ESP32
   - LoRa receiver
   - WiFi connectivity
   - MQTT client
   - Galvanic isolation stage
   - Valve and pump control circuitry

The control board receives soil moisture data through LoRa, processes irrigation logic, activates actuators (valves and pumps), and publishes system data to an MQTT broker.

A galvanic isolation stage was implemented to ensure safe and reliable separation between low-voltage logic and high-power actuation circuits, improving electrical noise immunity and system protection.
# Communication Flow
1. LoRa Communication
   - Long-range, low-power communication between monitoring and control nodes.
   - Enables future scalability across large agricultural areas.
2. MQTT Integration
   - The control board connects to an MQTT broker.
   - Sensor data and actuator states are published in real time.
   - Enables remote monitoring and control.
3. Node-RED Interface
   - Web-based dashboard.
   - Real-time soil moisture visualization.
   - Historical data monitoring.
   - Manual actuator control.
   - Connectivity status monitoring.
# Firmware Architecture
The control board was implemented using FreeRTOS, enabling:
- Concurrent task management
- Reliable scheduling of sensing, communication, and actuation
- Structured and scalable firmware design
- Deterministic system behavior
# Scalability Vision
MASIS was designed with expansion in mind. Future development may include:
- Multiple monitoring nodes per control unit
- Multi-zone irrigation
- Cloud database integration
- Predictive irrigation algorithms
- Energy optimization strategies
- Agricultural-scale deployment

The LoRa + MQTT architecture allows seamless integration of additional nodes without major redesign.
# Technologies Used
- ESP32 microcontrollers
- FreeRTOS
- LoRa communication
- MQTT protocol
- Node-RED
- Custom PCB design
- Galvanic isolation circuitry
# License
This project is licensed under the MIT License.
# Author
Developed as part of an Embedded Systems competition project focused on modular IoT-enabled smart irrigation systems.
Viridiana Meza Escobedo
