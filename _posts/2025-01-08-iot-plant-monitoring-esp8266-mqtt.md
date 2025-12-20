---
layout: post
title: "Building an IoT Plant Monitoring System (ESP8266 + MQTT + Flask)"
description: "End-to-end IoT plant monitoring system using ESP8266, MQTT, Flask, and SQLite, from sensors to real-time dashboard."
date: 2025-11-08
categories: blog projects iot
---

This project is an end-to-end **IoT Plant Monitoring System** designed to capture environmental data and display it in a real-time dashboard.

The main goal was to build a complete solution that connects:
**hardware → communication → backend → database → web dashboard**.

---

## The problem
Plant monitoring is a great real-world example of IoT because it requires:
- Continuous sensor readings  
- Reliable communication  
- Data storage  
- Visualization for decision-making  

I wanted to build a system that could realistically be extended to other monitoring scenarios.

---

## System overview
The system works as follows:

1. An **ESP8266** reads data from a **DHT11** sensor  
2. The ESP8266 publishes measurements using **MQTT**  
3. A Python service subscribes to MQTT messages  
4. Readings are stored in a local **SQLite** database  
5. A **Flask** web app displays a dashboard with charts in real time  

---

## Technologies used
- **ESP8266 (C++)** for embedded firmware  
- **DHT11** for temperature/humidity readings  
- **MQTT** for lightweight messaging  
- **Python** subscriber to process incoming data  
- **SQLite** for local persistence  
- **Flask + Bootstrap + Chart.js** for the dashboard  

This stack kept the project lightweight and easy to run locally while still being realistic.

---

## Key features
Some of the main features include:

- Sensor data collection (temperature and humidity)  
- JSON payload publishing via MQTT  
- Real-time data ingestion on the backend  
- Local database persistence  
- Web dashboard with live charts and history  

---

## Challenges and decisions
A key challenge was defining a data format that stayed consistent between the device and the backend.

To solve this, I focused on:
- Keeping payloads small and structured (JSON)  
- Using MQTT topics clearly  
- Logging and validating incoming messages before storing them  

Another important decision was choosing **SQLite** for fast local storage, which made testing and iteration easier.

---

## What I learned
This project helped me understand IoT systems in a complete way:
- How embedded devices publish data  
- How message brokers support communication  
- How to design a clean ingestion pipeline  
- How to connect databases to dashboards  

It also reinforced the idea that in IoT, the system is only as strong as its weakest layer.

---

## Next steps
Possible improvements include:
- Adding sensor calibration and better error handling  
- Supporting more sensors (soil moisture, light)  
- Authentication for remote access  
- Deployment on a Raspberry Pi or cloud VM  

---

**Repository:**  
https://github.com/renecano/IoT-Plant-Monitoring-System-ESP8266-MQTT-Flask-SQLite

---

**Repository:**  
https://github.com/renecano/grafos-fork-join-visualizer
