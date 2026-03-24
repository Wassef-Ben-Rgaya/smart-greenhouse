# 🌿 Smart Greenhouse System — IoT & AI Platform

<div align="center">

![Smart Greenhouse](https://img.shields.io/badge/IoT-Smart%20Greenhouse-green?style=for-the-badge&logo=raspberry-pi)
![AI](https://img.shields.io/badge/AI-YOLOv12%20%7C%20CNN%20%7C%20MobileNetV2-blue?style=for-the-badge&logo=tensorflow)
![Accuracy](https://img.shields.io/badge/Accuracy-92--95%25-brightgreen?style=for-the-badge)
![Flutter](https://img.shields.io/badge/Mobile-Flutter-02569B?style=for-the-badge&logo=flutter)
![Node.js](https://img.shields.io/badge/Backend-Node.js-339933?style=for-the-badge&logo=node.js)

**Final Year Engineering Project (PFE) — Computer Engineering | Polytech Tunis 2024/2025**

Developed by **Wassef BEN RGAYA** | Internship at **Shelly Tunisia**

</div>

---

## 📖 Overview

A fully automated **smart greenhouse system** that integrates IoT sensors, AI-powered plant monitoring, and a mobile application to autonomously control the greenhouse environment — optimizing plant growth while reducing energy consumption.

The system monitors and controls temperature, humidity, light intensity, and soil moisture in real time through a Raspberry Pi 4 central unit, a Node.js REST API, a Flutter mobile app, and AI models achieving **92–95% accuracy** in plant classification and growth prediction.

---

## 🗂️ Project Repositories

| Repository | Stack | Description |
|------------|-------|-------------|
| 🔧 [smart-greenhouse-backend](https://github.com/Wassef-Ben-Rgaya/smart-greenhouse-backend) | Node.js · Express · Firebase · InfluxDB | REST API, authentication, data management |
| 📱 [smart-greenhouse-mobile](https://github.com/Wassef-Ben-Rgaya/smart-greenhouse-mobile) | Flutter · Dart | Mobile app: KPIs, control, Grafana, alerts |
| 🤖 [smart-greenhouse-plant-prediction](https://github.com/Wassef-Ben-Rgaya/smart-greenhouse-plant-prediction) | Python · Flask · TensorFlow · YOLOv12 | Plant detection & growth prediction models |
| 🍓 [smart-greenhouse-iot](https://github.com/Wassef-Ben-Rgaya/smart-greenhouse-iot) | Python · Raspberry Pi | Sensor reading, actuator control, data pipeline |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    MOBILE APPLICATION                        │
│            smart-greenhouse-mobile (Flutter)                 │
│   KPIs · History · Manual Control · Alerts · Grafana        │
└────────────────────────┬────────────────────────────────────┘
                         │ REST API (JWT Auth)
                         ▼
          ┌──────────────────────────────┐
          │    smart-greenhouse-backend   │
          │       Node.js + Express       │
          └──────┬───────────┬────────────┘
                 │           │
        ┌────────▼───┐  ┌────▼──────┐  ┌───────────┐
        │  Firebase   │  │  InfluxDB  │  │  Grafana  │
        │  Firestore  │  │Time-series │  │ Dashboards│
        │  Realtime   │  │(1s/record) │  │           │
        └─────────────┘  └────────────┘  └───────────┘
                          ▲
          ┌───────────────────────────────────┐
          │        smart-greenhouse-iot         │
          │           Raspberry Pi 4            │
          └────────┬──────────┬────────────────┘
                   │          │
         ┌─────────▼──┐  ┌────▼──────────────────┐
         │   Sensors   │  │       Actuators         │
         │  DHT22      │  │  6 Relays               │
         │  TSL2561    │  │  Water Pump             │
         │  Soil       │  │  LED 30W                │
         │  DS3231     │  │  Fans / Heater          │
         └─────────────┘  └───────────────────────┘
                          ▲
          ┌───────────────────────────────────┐
          │  smart-greenhouse-plant-prediction  │
          │   Flask · YOLOv12 · CNN             │
          │   MobileNetV2 · 92–95% accuracy     │
          └───────────────────────────────────┘
```

---

## ✨ Key Features

### 🌡️ IoT Monitoring & Automation
- Real-time sensor reading every second (temperature, humidity, light, soil moisture)
- Automatic actuator control based on configurable thresholds per plant type
- 6-relay management: water pump, 30W LED grow light, fans, thermostat fan
- Local data backup with cloud sync every 5 minutes (offline-first)
- Local display on 7" touchscreen

### 📱 Mobile Application
- Real-time KPI dashboard with historical data
- Manual remote control of all actuators
- Push notifications & smart alerts
- Plant profile management (Spinach, Romaine Lettuce, Radish)
- Embedded Grafana dashboards
- User & admin role management

### 🤖 Artificial Intelligence
- Plant species classification: Spinach · Romaine Lettuce · Radish
- Growth stage prediction and plant health monitoring
- Models: **YOLOv12**, **CNN**, **MobileNetV2**
- Achieved accuracy: **92–95%**
- Served via Flask REST API

### 📊 Grafana Dashboards
- Temperature & ventilation/heating status
- Light intensity & LED lamp status
- Air & soil humidity monitoring
- Actuator runtime per hour analytics

---

## 🛠️ Tech Stack

### Hardware
| Component | Role |
|-----------|------|
| Raspberry Pi 4 | Central processing unit |
| DHT22 | Temperature & air humidity sensor |
| TSL2561 | Light intensity sensor |
| Soil moisture sensor | Irrigation decision making |
| DS3231 RTC | Real-time clock module |
| 6-Relay module | Actuator switching |
| 30W LED grow light | Plant lighting |
| Water pump | Automated irrigation |
| 7" Touchscreen | Local user interface |

### Software
| Layer | Technology |
|-------|------------|
| IoT scripts | Python 3 |
| REST API | Node.js · Express.js |
| Mobile app | Flutter · Dart |
| AI/ML models | Python · TensorFlow · Keras · Flask |
| Object detection | YOLOv12 |
| Time-series DB | InfluxDB |
| Cloud DB | Firebase Realtime Database · Firestore |
| Data visualization | Grafana |
| API deployment | Render |
| Remote access | WireGuard VPN |
| Project management | Scrum · 4 Sprints |

---

## 🌱 Supported Crops

| Plant | Optimal Temp | Optimal Humidity | Light |
|-------|-------------|-----------------|-------|
| 🥬 Romaine Lettuce | 15–20°C | 60–70% | Medium |
| 🌿 Spinach | 10–18°C | 50–65% | Low–Medium |
| 🌱 Radish | 10–18°C | 55–70% | Medium |

---

## 📈 Performance Metrics

| Metric | Value |
|--------|-------|
| AI model accuracy | **92–95%** |
| Sensor sampling rate | **Every 1 second** |
| Cloud sync frequency | **Every 5 minutes** |
| Greenhouse volume | **2 m³ prototype** |
| Managed actuators | **6 relays** |
| API deployment | **Render (cloud hosted)** |

---

## 🚀 Quick Start

```bash
# Backend API
git clone https://github.com/Wassef-Ben-Rgaya/smart-greenhouse-backend.git

# Mobile App
git clone https://github.com/Wassef-Ben-Rgaya/smart-greenhouse-mobile.git

# AI / Plant Prediction
git clone https://github.com/Wassef-Ben-Rgaya/smart-greenhouse-plant-prediction.git

# IoT / Raspberry Pi
git clone https://github.com/Wassef-Ben-Rgaya/smart-greenhouse-iot.git
```

Refer to each repository's `README.md` for specific setup instructions.

---

## 👨‍💻 Author

**Wassef BEN RGAYA**
Computer Engineering — AI & Data Science Specialization

📍 Nabeul, Tunisia
📧 wassefbenrgaya24@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/wassef-ben-rgaya-600817188)
🐙 [GitHub](https://github.com/Wassef-Ben-Rgaya)

---


## 📄 License

This project was developed as part of a Final Year Engineering Project (PFE) at Polytech Tunis.
© 2025 Wassef BEN RGAYA — All rights reserved.
