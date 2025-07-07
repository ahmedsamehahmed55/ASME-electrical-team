# ASME-electrical-team
Motor drivers and serial communication
Encoders and CAN modules and Picos 
Overview
motors and decisions for the gear box
Presenting Circuit diagrams 
some cad stuf

# 🚀 NASA Lunabotics 2024 – Electrical Subsystem

Welcome to the official repository for the electrical subsystem of the University of Miami’s ASME Lunabotics team for the **2024 NASA Lunabotics Competition**.

---

## 📚 Table of Contents

- [Project Overview](#project-overview)  
- [Achievements](#achievements)  
- [Responsibilities](#responsibilities)  
- [Electrical System Architecture](#electrical-system-architecture)  
- [CAN bus](#CAN-bus)
- [How to Run](#how-to-run)  
- [Motor drivers](#Motor-drivers)  
- [License](#license)

---

## 📌 Project Overview

This project highlights my role as the **electrical co-lead** of the University of Miami’s **ASME Lunabotics team** for the **2024 NASA Lunabotics Competition** — a nationally recognized challenge that tasks university teams with designing and building autonomous lunar excavators capable of navigating and collecting regolith in a simulated lunar environment.

Without hesitation, the **2024 season marked a pivotal turning point** for our team. We built multiple subsystems entirely from scratch, including the complete **electrical subsystem**.

We prioritized **simplicity and reliability**, focusing on minimizing points of failure while ensuring robust performance in harsh simulated lunar conditions. The rover operated flawlessly during competition.

---

## 🏆 Achievements

- 🏅 **Leaps and Bounds Award** – For significant improvements in systems engineering  
- 🥉 **3rd Place in Presentation and Demonstration**  
- ⚡ **Most Energy-Efficient Team**

---

## 🛠 Responsibilities

As co-lead of the electrical team, my key responsibilities included:

- ⚡ Designing and implementing the rover’s electrical architecture  
- 🔋 Power distribution and battery management  
- 🧠 Motor driver selection and integration  
- 📡 Sensor interfacing and real-time data communication  
- 🛜 CAN communication between microcontrollers and subsystems  
- 🛠 PCB design, prototyping, and testing  
- 🔎 Debugging and ensuring system reliability in field conditions

---

## 🔌 Electrical System Architecture

<p align="center">
  <img src="2024-2025/assets/Circuits/Motors.png" alt="Lunabotics Rover 2024" width="600"/>
</p>
<p align="center">
  <img src="2024-2025/assets/rover/Rover.jpg" alt="Lunabotics Rover 2024" width="600"/>
</p>
<p align="center">
  <b>NASA Lunabotics 2024 – Fully Assembled Rover</b><br>
  <a href="2024-2025/assets/">📸 See More Photos</a>
</p>

Key components included:

- 12V Li-ion Battery Pack  
- Custom PCBs with regulated 5V/3.3V rails  
- CAN Bus topology for subsystem communication  
- Motor drivers (e.g., BTS7960 or others)  
- Microcontroller (e.g., STM32 / Arduino / Teensy)  
- Sensors: IMU, encoders, limit switches, voltage/current monitors

---

## 💻 Technologies Used

- 🖥 Embedded C / C++  
- 🧩 Arduino / STM32 / Teensy  
- 📡 CAN Bus (Controller Area Network)  
- 🛠 EasyEDA / KiCad for PCB design  
- 📈 Logic analyzers and multimeters for debugging  
- ⚙️ Git and GitHub for version control  
- 📑 Documentation tools (Markdown, Google Docs, etc.)

---

## 💻 Motor drivers (Sabertooth)
One of the challenges we faced was the voltage incompatibility between the Raspberry Pi, which operates at 3.3V logic, and the Sabertooth motor driver, which requires 5V logic for reliable serial communication. In the 2023 competition, the team addressed this issue by routing control signals through an Arduino, which acted as a 5V buffer. While this worked, it introduced unnecessary complexity and potential communication delays. To make the system simpler and reduce the points of failure, we transitioned to using compact bi-directional logic level converters, allowing us to safely and efficiently shift the 3.3V signals up to 5V. This solution maintained signal integrity and enabled direct communication between the Pi and the Sabertooth.



To test the motors, we wrote a script using the `pysabertooth` library. Each Sabertooth was initialized with a unique address. This script demonstrates safe testing under current limitations and includes logic for bidirectional control.

### 🔧 Sample Code Snippet

```python
from pysabertooth import Sabertooth

# Initialize Sabertooth motor driver on address 128
motor1 = Sabertooth("/dev/serial0", baudrate=9600, address=128)
motor1.open()
motor1.drive(1, 60)  # Drive motor 1 at 60% power
motor1.drive(2, 60)  # Drive motor 2 at 60% power
```

👉 View the full motor test script [here](scripts/lunabotics_motor_test.py)


<p align="center">
  <img src="2024-2025/assets/Circuits/Motors.png" alt="Lunabotics Rover 2024" width="600"/>
</p>
---

## ▶️ How to Run

> _Instructions for replicating or simulating the system (if applicable)._

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/nasa-lunabotics-2024-electrical.git


* A **diagram** or image of the electrical system
* Sections for **Setup**, **Hardware List**, or **Team Credits**
* A **"Tech Stack"** or component list (e.g., Arduino, CAN transceivers, motor drivers, etc.)

I'm happy to build out the full `README.md` with more sections if you'd like!
