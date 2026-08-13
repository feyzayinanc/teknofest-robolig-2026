# TEKNOFEST Robolig 2026 – Remote Controlled Cargo Robot

A remote-controlled cargo robot system designed for the **TEKNOFEST 2026 Robolig competition application**.

The project combines a four-wheel mobile platform, robotic arm, RFID-based cargo identification, wireless communication and a telescopic zipline mechanism into a modular robotic system.

> **Team:** UmayTech
> **Project:** Remote Controlled Cargo Robot
> **Competition:** TEKNOFEST 2026 Robolig

## Project Overview

The main objective of the project is to identify cargo using RFID tags, transport the cargo to designated delivery points and complete the required route using the robot's mechanical and electronic subsystems.

The system was designed as a modular architecture consisting of:

* Four-wheel drive mobile platform
* Robotic arm and gripper mechanism
* RFID-based cargo identification
* OLED information display
* Wireless remote control
* Telescopic zipline mechanism
* Central electronic control system

The main vehicle control is based on **Deneyap Kart 1A**, while a **Deneyap Kart Mini** is used for the remote-control unit. Communication between the vehicle and controller is designed using the **ESP-NOW** protocol.

## System Architecture

The robot consists of several interconnected subsystems:

```text
Remote Controller
Deneyap Kart Mini
        │
        │ ESP-NOW
        ▼
Deneyap Kart 1A
        │
        ├── DC Motor Drivers ──► 4WD Drive System
        │
        ├── PCA9685 ──► Robotic Arm & Zipline Servos
        │
        ├── MFRC522 ──► RFID Cargo Identification
        │
        └── OLED Display ──► Delivery Information
```

The modular architecture was designed to make maintenance, troubleshooting and future development easier.

## Main Technologies & Components

### Control & Communication

* Deneyap Kart 1A
* Deneyap Kart Mini
* ESP-NOW
* C/C++ / Arduino-based development

### Motor & Motion Control

* Four DC geared motors
* BTS7960 / IBT-2 motor drivers
* PCA9685 16-channel PWM servo driver
* Eight servo motors in the detailed electronic design
* Telescopic tower drive motor

### Identification & Display

* MFRC522 RFID reader
* RFID tags
* 0.96" OLED display
* SPI communication
* I2C communication

### Power System

The vehicle power architecture was designed using separate power paths for high-current motors and sensitive control electronics.

* 3S 11.1V Li-Po battery
* 2S 7.4V Li-Po battery
* 5V DC-DC buck converter
* 6V DC-DC buck converter
* TP4056 charging module
* Fuse and power protection structure

The separation of the motor and control power paths is intended to reduce the effect of sudden motor current demands on sensitive electronic components.

## Robotic Arm

The robotic arm was designed for cargo collection and transportation.

The mechanical design uses a compact five-axis "scorpion-form" structure to provide controlled movement within the limited vehicle volume.

The gripper mechanism is used to securely hold the cargo and transfer it to the vehicle's transportation area.

## RFID Cargo Identification

The RFID subsystem identifies the cargo using its RFID tag.

The workflow is:

```text
RFID Tag
   ↓
MFRC522 Reader
   ↓
UID Data
   ↓
Deneyap Kart 1A
   ↓
City / Delivery Matching
   ↓
OLED Display
```

The RFID reader communicates with the Deneyap Kart 1A using SPI, while the OLED display uses I2C communication.

## Zipline Mechanism

One of the main mechanical features of the project is the telescopic zipline mechanism.

The system was designed with:

* Telescopic tower
* Lead screw mechanism
* Rail mechanism
* Bearing-based rope connection
* Servo-controlled locking mechanism
* Pin locking mechanism

During the zipline operation, the tower rises to reach the line, the connection mechanism locks onto the rope and the locking pin secures the system.

## Mechanical Design

The vehicle was designed according to the physical constraints of the competition environment.

The design process included:

* Competition track analysis
* Digital modeling in SketchUp
* Chassis design
* Robotic arm design
* Telescopic tower design
* Ramp and obstacle considerations

The planned vehicle dimensions are approximately **58 × 48 × 58 cm**, with a target total weight below **20 kg**.

The wheels have an approximate diameter of **12 cm**.

## Software Architecture

The software architecture is divided into five main modules:

1. Movement control
2. Robotic arm control
3. Zipline control
4. RFID reading
5. OLED display

The modular software structure is intended to improve code readability, maintenance and future development.

The main operational flow is:

```text
System Initialization
        ↓
Remote Control Data
        ↓
Movement Control
        ↓
Cargo Collection
        ↓
RFID Identification
        ↓
Delivery Information
        ↓
Cargo Delivery
        ↓
Zipline Operation
        ↓
Return
        ↓
Repeat
```

## Project Documentation

The project documentation includes:

* Project Design Report (PDR)
* System architecture
* Electronic design
* Mechanical design
* Software architecture
* Bill of Materials (BOM)
* Production planning
* Project methodology

## Team

The project was developed by an interdisciplinary student team covering software, electronics and mechanical design.

| Team Member         | Field                     | Responsibility                   |
| ------------------- | ------------------------- | -------------------------------- |
| Ceyda Halide Yazıcı | Software Engineering      | Team Captain, Electronics Design |
| Dila Betül Şanlıer  | Software Engineering      | Software Design, Coding          |
| Feyza Nur Yınanç    | Computer Engineering      | Electronics Design               |
| Merve Şengül        | Software Engineering      | Software Design, Coding          |
| Ömer Faruk Yazıcı   | Architectural Restoration | Mechanical Design, Modeling      |

## Project Status

This project was developed as part of the **TEKNOFEST 2026 Robolig competition application**.

The repository documents the project's system architecture, mechanical concepts, electronic design and software approach.

## References

* Türkiye Teknoloji Takımı Vakfı – Deneyap Kart 1A
* Espressif Systems – ESP-NOW
* Fortune Semiconductor – TP4056
* NXP Semiconductors – PCA9685
* NXP Semiconductors – MFRC522
* Solomon Systech – SSD1306 OLED Driver

---

**UmayTech – TEKNOFEST Robolig 2026**
