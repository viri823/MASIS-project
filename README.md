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
