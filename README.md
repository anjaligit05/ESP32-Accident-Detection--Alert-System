# ESP32-Accident-Detection--Alert-System
This project is an IoT-based accident detection and emergency alert system developed using ESP32, MPU6050 accelerometer/gyroscope and GPS. The system detects abnormal motion or impact conditions and sends real-time accident alerts with location information through a Telegram Bot, helping provide faster emergency notification.
# Project Overview 

The ESP32 Accident Detection & Alert System is an IoT-based safety prototype designed to detect potential accident conditions using an MPU6050 accelerometer and gyroscope.

When abnormal acceleration is detected, the ESP32 processes the sensor data and obtains the current location using a NEO-6M GPS module. An emergency alert containing the accident status and GPS location is then sent through a Telegram Bot.

The system also uses a buzzer to provide a local warning when a potential accident is detected.
# Objectives

- Detect sudden acceleration or impact conditions using MPU6050.
- Obtain geographical location using NEO-6M GPS.
- Send real-time emergency notifications through Telegram Bot.
- Provide a local buzzer alert during accident detection.
- Demonstrate IoT-based emergency communication using ESP32.
  # Features

- 🚗 Potential accident/impact detection
- 📡 ESP32-based IoT connectivity
- 📍 GPS location tracking
- 📱 Telegram emergency notification
- 🔔 Local buzzer alert
- 📊 Real-time sensor data processing
- 🌐 Wi-Fi connectivity
- 🧩 Modular sensor interfacing
- ## 🛠️ Hardware Components

| Component | Purpose |
|-----------|---------|
| ESP32 | Main microcontroller and Wi-Fi connectivity |
| MPU6050 | Accelerometer and gyroscope for motion detection |
| NEO-6M GPS | Obtains geographical location |
| Buzzer | Provides local emergency alert |
| Breadboard | Prototype circuit assembly |
| Jumper Wires | Electrical connections |
| USB Power Supply | Powers the ESP32 |

## 💻 Software & Technologies
- Arduino IDE
- C/C++
- ESP32
- Arduino WiFi Library
- MPU6050 Library
- TinyGPS++ Library
- UniversalTelegramBot Library
- Telegram Bot API
- ## 🏗️ System Architecture

```text
          ┌──────────────────┐
          │     MPU6050      │
          │ Accelerometer &  │
          │    Gyroscope     │
          └────────┬─────────┘
                   │
                   │ I2C
                   ▼
          ┌──────────────────┐
          │      ESP32       │
          │ Data Processing  │
          │ & Decision Logic │
          └───────┬────┬─────┘
                  │    │
             UART │    │ Wi-Fi
                  │    │
                  ▼    ▼
          ┌──────────┐ ┌──────────────┐
          │ NEO-6M  │ │ Telegram Bot │
          │   GPS   │ │   Service    │
          └────┬─────┘ └──────┬───────┘
               │              │
               │ Location     │ Alert
               ▼              ▼
          GPS Coordinates   Smartphone

## Pin Connections
MPU6050 → ESP32
MPU6050
ESP32
VCC
3.3V
GND
GND
SDA
GPIO 21
SCL
GPIO 22
NEO-6M GPS → ESP32
NEO-6M
ESP32
VCC
According to module specification
GND
GND
TX
GPIO 16 (RX2)
RX
GPIO 17 (TX2)
Buzzer → ESP32
Buzzer
ESP32
+
GPIO 25
-
GND
GPIO 25
-
GND
                               
                  ESP32
                    │
                    ▼
                 Buzzer
              Local Warning

 ## ⚙️ Working Principle
Step 1 — Motion Detection
The MPU6050 continuously measures acceleration and angular motion.
Step 2 — Accident Detection
The ESP32 calculates the acceleration magnitude and compares it with a predefined threshold.
If the measured acceleration exceeds the threshold, the system considers it a potential accident event.
Step 3 — GPS Location
After detecting a potential accident, the ESP32 reads the GPS data from the NEO-6M module.
Step 4 — Emergency Alert
The ESP32 connects to the configured Wi-Fi network and sends an emergency message through the Telegram Bot.
Step 5 — Location Sharing
If valid GPS coordinates are available, the alert includes a Google Maps location link.
Step 6 — Local Warning
The buzzer is activated to provide a local audible indication of the detected event.
