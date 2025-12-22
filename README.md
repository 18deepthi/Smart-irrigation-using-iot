# 🌱 Smart Irrigation System Using IoT

## 📌 Project Overview
The **Smart Irrigation System using IoT** is an automated agriculture solution that monitors **soil moisture, temperature, and humidity** and controls a **water pump automatically** using sensor data.

This system helps reduce water wastage, minimizes manual intervention, and improves irrigation efficiency.  
Although implemented using Arduino, it can be easily extended to full IoT by integrating Wi-Fi modules like **ESP8266 / NodeMCU**.

---

## 🎯 Objectives
- Automate irrigation based on soil moisture
- Reduce water wastage
- Improve crop productivity
- Enable sensor-based decision making

---

## 🛠 Tech Stack
- **Microcontroller:** Arduino Uno / Nano / Mega  
- **Sensors:**  
  - DHT11 (Temperature & Humidity)  
  - Soil Moisture Sensor  
- **Actuators:** Relay Module, Water Pump  
- **Display:** 16x2 LCD  
- **Programming Language:** Embedded C / Arduino IDE  

---

## 🚀 Features
- Real-time soil moisture monitoring
- Temperature and humidity sensing
- Automatic motor ON/OFF control
- Live sensor readings displayed on LCD
- Configurable moisture threshold
- Easy extension to IoT platforms

---

## 🔌 Hardware Components
- Arduino Board  
- DHT11 Sensor  
- Soil Moisture Sensor  
- Relay Module  
- Water Pump / DC Motor  
- 16x2 LCD Display  
- Jumper Wires, Breadboard, Power Supply  

---

## 🔗 Pin Connections

### LCD (16x2)
- RS → 7  
- E → 8  
- D4 → 9  
- D5 → 10  
- D6 → 11  
- D7 → 12  

### Sensors & Relay
- **DHT11 Signal** → D5  
- **Soil Moisture Sensor** → A0  
- **Relay IN** → D6  
- **Relay VCC** → 5V  
- **Relay GND** → GND  

⚠️ Use low-voltage DC pump for safety during demonstrations.

---

## 🧪 Working Logic
- Soil moisture is read using analog pin A0  
- Sensor value is mapped to percentage (0–100%)  
- If moisture < 30% → Motor ON  
- If moisture ≥ 30% → Motor OFF  
- Temperature and humidity are read using DHT11  
- All readings and motor status are displayed on LCD  

---

## 📦 Required Libraries
- LiquidCrystal (built-in)  
- DHT sensor library  

---

## 🌐 Future Enhancements (IoT Extension)
- Integrate ESP8266 / NodeMCU for Wi-Fi
- Cloud data upload (ThingSpeak, Firebase, MQTT)
- Mobile app control (Blynk)
- Historical data analytics and graphs
- Remote motor control

---

## 📚 What I Learned
- Sensor integration with microcontrollers
- Automating real-world systems
- Relay-based motor control
- Embedded programming using Arduino
- Basics of IoT system design

---
