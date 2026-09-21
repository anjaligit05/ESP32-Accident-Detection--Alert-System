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
- 
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

# 💻 Software & Technologies
- Arduino IDE
- C/C++
- ESP32
- Arduino WiFi Library
- MPU6050 Library
- TinyGPS++ Library
- UniversalTelegramBot Library
- Telegram Bot API
 # 🏗️ System Architecture

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
```

# 🔌 Pin Connections

### MPU6050 → ESP32

| MPU6050 Pin | ESP32 Pin |
|---|---|
| VCC | 3.3V |
| GND | GND |
| SDA | GPIO 21 |
| SCL | GPIO 22 |

### NEO-6M GPS → ESP32

| GPS Pin | ESP32 Pin |
|---|---|
| VCC | According to module specification |
| GND | GND |
| TX | GPIO 16 (RX2) |
| RX | GPIO 17 (TX2) |

### Buzzer → ESP32

| Buzzer Pin | ESP32 Pin |
|---|---|
| + | GPIO 25 |
| − | GND |


                               
               

#  ⚙️ Working Principle

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

- ## Project Structure


ESP32-Accident-Detection-Alert-System/
│
├── README.md
│
├── src/
│   └── accident_detection.ino
│
├── circuit/
│   ├── circuit_diagram.jpg
│   ├── system_architecture_diagram.png
│   └── PIN_CONNECTIONS.md
│
├── images/
│   ├── project_hardware_setup.jpg
│   └── telegram_alert.jpg
│
├── docs/
│   └── project_report.pdf
│
├── LICENSE
└── .gitignore

 # 🧪 Testing

The prototype can be tested using the following conditions:
Test
Expected Result
Normal movement
No emergency alert
Sudden acceleration
Potential accident detected
GPS available
Location included in alert
Wi-Fi connected
Telegram notification sent
Buzzer enabled
Local warning generated

 # 🔧 Configuration


The accident detection threshold is configurable in the source code.
const float ACCIDENT_THRESHOLD_G = 2.5;
The threshold should be calibrated according to the actual hardware, mounting conditions and testing environment.

# 📈 Future Scope


Add GSM/4G communication for areas without Wi-Fi.
Add vehicle ignition monitoring.
Add cloud-based accident logging.
Develop a dedicated Android application.
Add automatic emergency contact notification.
Improve accident detection using sensor fusion.
Add a confirmation/cancellation mechanism to reduce false alerts.
Improve GPS reliability and location accuracy.

 - # 🎓 Skills Demonstrated
This project demonstrates practical experience with:
Embedded C/C++
ESP32 programming
IoT development
Sensor interfacing
I2C communication
UART communication
GPS integration
Wi-Fi connectivity
Telegram Bot API
Hardware debugging
Embedded system design
Git and GitHub

 # ⚠️ Limitations


This project is an academic/prototype implementation.
The acceleration threshold used for detecting potential accidents is not a certified automotive safety algorithm. Real-world deployment would require extensive testing, calibration, sensor fusion and safety validation.

# 👩‍💻 Author


Anjali Kumari
B.Tech – Electronics & Communication Engineering
Galgotias College of Engineering and Technology

# 📄 License

This project is available under the MIT License.

