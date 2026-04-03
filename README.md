# IOT-based-seed-sprayer-
IoT based automatic seed sprayer using ESP32 and soil moisture sensor
# 🌱 IoT Based Seed Sprayer System

## 📌 Introduction
The IoT Based Seed Sprayer is an automated smart farming system that sprays seeds or water based on soil moisture conditions. It uses ESP32 for IoT connectivity and automation.

---

## 🎯 Objective
- Automate seed spraying process  
- Reduce manual effort  
- Save water using smart irrigation  
- Enable remote monitoring  

---

## ⚙️ Components Used
- ESP32 Microcontroller  
- Soil Moisture Sensor  
- Relay Module  
- Water Pump / Motor  
- Power Supply  
- Connecting Wires  

---

## 🧠 Working Principle
1. Soil moisture sensor reads soil condition  
2. ESP32 processes sensor data  
3. If soil is dry → Relay ON → Pump starts  
4. If soil is wet → Relay OFF → Pump stops  
5. Data can be monitored using IoT platform  

---

## 🌐 IoT Integration
- WiFi enabled using ESP32  
- Can connect with Blynk / ThingSpeak  
- Remote monitoring possible  

---

## 🚀 Features
- Automatic spraying system  
- Smart irrigation  
- Low cost  
- Water efficient  
- Easy to use  

---

## 📷 Project Images

### 🔹 Setup Image
![Project Setup](https://via.placeholder.com/600x300?text=Seed+Sprayer+Setup)

### 🔹 Working Model
![Working Model](https://via.placeholder.com/600x300?text=Working+Model)

---

## 🔌 Circuit Diagram
![Circuit Diagram](https://via.placeholder.com/600x300?text=Circuit+Diagram)

---

## 💻 ESP32 Code

```cpp
#define sensorPin 34
#define relayPin 26

int sensorValue = 0;
int threshold = 500;

void setup() {
  Serial.begin(115200);
  pinMode(relayPin, OUTPUT);
  digitalWrite(relayPin, HIGH); // Pump OFF initially
}

void loop() {
  sensorValue = analogRead(sensorPin);
  Serial.println(sensorValue);

  if(sensorValue > threshold) {
    digitalWrite(relayPin, LOW);  // Pump ON
    Serial.println("Soil Dry - Pump ON");
  } else {
    digitalWrite(relayPin, HIGH); // Pump OFF
    Serial.println("Soil Wet - Pump OFF");
  }

  delay(2000);
}
