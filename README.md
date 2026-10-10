# Smart Home System 🏠

An embedded **Smart Home System** that controls lighting (with dimming), air conditioning, door access, and alarms. The home can be managed remotely from a **mobile app over Bluetooth**, or locally through an **LCD and keypad** interface.

This was the graduation project of the **Embedded Systems Diploma** at **AMIT Learning** (175 hours, Oct 2023 – Mar 2024).

---

## Table of Contents

- [Features](#features)
- [System Overview](#system-overview)
- [Hardware](#hardware)
- [Software Architecture](#software-architecture)
- [Control Interfaces](#control-interfaces)
- [Getting Started](#getting-started)
- [Skills Applied](#skills-applied)
- [Team](#team)
- [Acknowledgements](#acknowledgements)

---

## Features

| Feature              | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| 💡 **Lamp control**  | Turn lamps on and off, with **dimming** support                             |
| ❄️ **Air conditioning** | Controlled automatically based on readings from a **temperature sensor** |
| 🚪 **Door access**   | Door opened and closed with a **servo motor**                               |
| 🚨 **Alarm**         | Alarm system for home security                                              |
| 📱 **Mobile control**| Manage the system wirelessly from a phone over **Bluetooth**                |
| ⌨️ **Local control** | Operate the system on site with an **LCD** and **keypad**                   |

## System Overview

```
        ┌──────────────┐   Bluetooth    ┌──────────────────────────┐
        │  Mobile app  │ ◄────────────► │                          │
        └──────────────┘                │                          │
                                        │      Microcontroller     │
        ┌──────────────┐                │                          │
        │ Keypad + LCD │ ◄────────────► │                          │
        └──────────────┘                └────────────┬─────────────┘
                                                     │
              ┌────────────────┬─────────────────────┼──────────────────┬──────────────┐
              ▼                ▼                     ▼                  ▼              ▼
        Lamps (dimming)   Temperature sensor    Air conditioner    Servo (door)     Alarm
```

## Hardware

| Component                  | Purpose                                         |
|----------------------------|-------------------------------------------------|
| Microcontroller            | _Add your MCU here_                             |
| Bluetooth module           | Wireless link to the mobile app                 |
| LCD                        | Local display                                   |
| Keypad                     | Local input                                     |
| Temperature sensor         | Room temperature measurement for the A/C logic  |
| Servo motor                | Door lock / opening mechanism                   |
| Lamps with dimming control | Lighting                                        |
| Air conditioner (or relay) | Cooling                                         |
| Alarm / buzzer             | Security alert                                  |

> Update this table with the exact parts and pin connections you used.

## Software Architecture

The firmware is written in **embedded C**. A typical layered structure for a project like this:

```
├── MCAL/        # Microcontroller drivers (DIO, ADC, Timers/PWM, UART, ...)
├── HAL/         # Device drivers (LCD, Keypad, Temperature sensor, Servo, Bluetooth, Lamp, Buzzer)
├── APP/         # Application logic (lamp, A/C, door, alarm, user interfaces)
├── main.c
└── README.md
```

> Adjust this tree to match your actual repository.

## Control Interfaces

**Mobile / Bluetooth**
Commands sent from the phone over Bluetooth are received by the microcontroller and used to switch lamps, set the dimming level, control the door, and manage the alarm.

**Local (LCD and keypad)**
The same functions are available on site: the user navigates options on the LCD and enters choices on the keypad.

## Getting Started

1. Clone the repository:
   ```bash
   git clone <your-repository-url>
   cd <repository-folder>
   ```
2. Open the project in your IDE or toolchain for your microcontroller.
3. Wire the hardware according to the pin table above.
4. Build and flash the firmware.
5. Pair your phone with the Bluetooth module and send commands, or use the keypad and LCD.

## Skills Applied

- Embedded C programming and data structures
- Interfacing protocols (UART/Bluetooth, and the peripherals above)
- Sensor interfacing and actuator control (temperature sensor, servo motor, dimming)
- Embedded systems tools and testing/validation practices
- IoT concepts and wireless control

## Team

| Name                 | LinkedIn                                                                 |
|----------------------|--------------------------------------------------------------------------|
| Waad Rabie           | [Profile](https://www.linkedin.com/in/waad-rabie-592829273/)             |
| Rawan Khaled         | [Profile](https://www.linkedin.com/in/rawan-khaled-72447032b/)                                                                         |
| Nour Sameh           | [Profile](https://www.linkedin.com/in/nour-sameh-/)                      |
| Nour Ayman Zaghloul  | [Profile](https://www.linkedin.com/in/nour-ayman-zaghloul-naz/)          |

## Acknowledgements

Thank you to **AMIT Learning** and our instructors:

- [Fathi Mandour](https://www.linkedin.com/in/fathi-mandour-046315203/)
- [Kareem Hussein](https://www.linkedin.com/in/kareemhusseint/)
