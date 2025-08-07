# 🤖 Arduino-Based Human Following Robot

An intelligent robot built using Arduino that can detect and follow a person using ultrasonic sensors. This is a beginner-friendly DIY robotics project focused on embedded systems, sensor integration, and basic autonomous decision-making.

## 🚀 Project Overview

This project features a robot car that follows a human by continuously scanning its surroundings using **three ultrasonic sensors**. Based on the sensor data, it makes directional decisions (forward, left, right) and avoids obstacles.

## 🎯 Features

- 🚶‍♂️ Human-following behavior using distance detection
- 🔄 Real-time decision making with multiple ultrasonic sensors
- 🔌 Powered by Arduino UNO
- ⚙️ Smooth motor control via L298N driver
- 🧱 Simple and modular hardware setup

---

## 🧰 Components Required

| Component                | Quantity |
|--------------------------|----------|
| Arduino UNO              | 1        |
| Ultrasonic Sensor (HC-SR04) | 3        |
| L298N Motor Driver       | 1        |
| DC Motors (BO type)      | 2        |
| Robot Chassis (with wheels) | 1        |
| Li-ion Battery Pack (7.4V or 12V) | 1        |
| Jumper Wires             | ~20      |
| Breadboard (optional)    | 1        |
| Power Switch             | 1        |

---

## 🔌 Wiring & Circuit Diagram

- **Ultrasonic Sensors**:
  - Front Sensor → Trigger: D2, Echo: D3
  - Left Sensor → Trigger: D4, Echo: D5
  - Right Sensor → Trigger: D6, Echo: D7

- **Motor Driver (L298N)**:
  - IN1 → D8
  - IN2 → D9
  - IN3 → D10
  - IN4 → D11
  - Motor A & B → Connected to wheels
  - VCC → Battery (7.4V+)
  - GND → Arduino GND

- **Power**:
  - Arduino can be powered via VIN from the L298N or USB (for testing)
  - Motors powered via battery through L298N

---

## 🧠 Code Logic Summary

```cpp
// Pseudo-logic:
loop() {
    Read all three ultrasonic sensors;
    If front sensor detects object within 30 cm:
        moveForward();
    Else if left < right:
        turnLeft();
    Else if right < left:
        turnRight();
    Else:
        stop();
}
