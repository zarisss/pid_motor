# PID-Based DC Motor Position Control using Encoder (Arduino)

This project implements **position control of a DC motor** using a **rotary encoder** and a **simple PID controller**. The system runs on an Arduino, takes a fixed distance (in cm), converts it to encoder ticks, and drives the motor precisely to that position.

---

##  Features

- Encoder feedback via interrupt (`attachInterrupt`)
- PID control loop (P, I, D terms configurable)
- Clean motor direction logic with H-bridge (e.g., L298N)
- Real-time position vs. target output over Serial
- Can be extended to take user input via Serial

---

## System Behavior

- Target distance is hardcoded in `target_cm`
- Code converts this distance to encoder ticks via `cvrt` (ticks/cm)
- The motor runs and stops when the target position is reached
- Serial monitor prints current position and target continuously

---

## Hardware Required

| Component         | Description                          |
|------------------|--------------------------------------|
| Arduino Uno/Nano | Main controller                      |
| DC Motor          | With encoder (quadrature preferred) |
| L298N Motor Driver| For direction + speed control       |
| Rotary Encoder    | Connected to pins 2 & 3             |
| Power Supply      | As per motor spec                   |

### Wiring (Example)

| Arduino Pin | Connected To         |
|-------------|----------------------|
| D2          | Encoder A (ENCA)     |
| D3          | Encoder B (ENCB)     |
| D5          | L298N ENA (PWM)      |
| D6          | L298N IN1            |
| D7          | L298N IN2            |
| 5V/GND      | Power as required    |

---

### Circuit Diagram
<img width="932" height="616" alt="image" src="https://github.com/user-attachments/assets/fd3723c6-2c41-4f92-871a-97bc52dbd39d" />
