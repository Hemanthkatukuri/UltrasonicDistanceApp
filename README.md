# 🚘 Ultrasonic Distance Monitoring with MQTT

This project simulates a **Forward Collision Avoidance System (FCAS)** using an **ultrasonic sensor**, **CC3200 LaunchPad**, and a **Java-based Android application**. It uses the **MQTT protocol** to wirelessly transmit sensor readings to the app in real-time.

---

## 🧰 Hardware Used

- **TI CC3200 LaunchPad** – WiFi-enabled microcontroller
- **Grove Ultrasonic Ranger v2.0** – For distance measurement
- **Grove BoosterPack** – For connecting Grove modules
- **Buzzer + Red LED (D7 onboard)** – Simulates emergency alerts

---

## 📲 Android App (Java)

A lightweight mobile application built using **Java in Android Studio** that subscribes to MQTT topics and displays the distance in real time with visual status indicators.

### ✅ Features:
- Connects to HiveMQ broker using MQTT
- Displays live distance data in centimeters
- Color-coded safety levels with animated indicators:
  - 🟢 **SAFE**: ≥ 50 cm
  - 🟠 **BE ALERT**: 25–49 cm
  - 🔴 **DANGER**: 10–24 cm
  - 🚨 **CRITICAL**: < 10 cm (buzzer ON)

### 📡 MQTT Configuration:
- **Broker**: `broker.hivemq.com`
- **Port**: `1883`
- **Topic**: `ultrasonic/distance`

### 🖼 Sample UI Indicators:
| Distance Range | Status     | UI Indicator |
|----------------|------------|--------------|
| ≥ 50 cm        | SAFE       | Green LED    |
| 25–49 cm       | BE ALERT   | Orange LED   |
| 10–24 cm       | DANGER     | Red LED      |
| < 10 cm        | CRITICAL   | Buzzer ON    |

---

## 🔌 Energia Firmware (CC3200)

The CC3200 continuously measures the distance using the ultrasonic sensor and publishes the result to an MQTT topic.

### 🔄 Sensor → MQTT Broker Flow:
1. Trigger ultrasonic pulse and read echo
2. Calculate distance in cm
3. Activate LED or buzzer based on thresholds
4. Publish distance to topic `ultrasonic/distance`

### 🧪 Sample Payload:
  Distance: 22

### 📦 Libraries Used:
- `WiFi.h`
- `MQTTClient.h`
- `Ultrasonic.h`

---

## 💡 Future Enhancements
- Multi-sensor support (for front, rear, and side)
- Data logging and chart visualization
- Real motor control simulation
- Firebase or cloud integration for analytics

---

## 👨‍💻 Developed By

**Hemanth Katukuri**    
- CC3200, MQTT, Java, Energia  

