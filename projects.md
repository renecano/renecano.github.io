---
layout: page
title: Projects
permalink: /projects/
description: Software, data, and IoT projects developed by René Cano, ITC student at Tecnológico de Monterrey.
---

Here are some of my main projects. Each includes a short overview, key highlights, and a repository link.

---

<div class="grid">

  <div class="card">
    <div class="card-title">Sales & Inventory Registration System (Streamlit App)</div>
    <div class="card-text">
      Web application for small businesses to record sales, manage products, and view basic metrics.
    </div>
    <ul>
      <li>Product registration</li>
      <li>Sales log</li>
      <li>Dashboards & simple reports</li>
      <li>Clean, minimal UI</li>
      <li>PostgreSQL support</li>
    </ul>
    <div class="card-actions">
      <a class="btn btn-primary" href="https://github.com/renecano/ventas-inventario-streamlit" target="_blank" rel="noopener">Repository</a>
      <a class="btn btn-ghost" href="/blog/projects/sales-inventory-system/">Case study</a>
    </div>
  </div>

  <div class="card">
    <div class="card-title">IoT Plant Monitoring System (ESP8266 + MQTT + Flask + SQLite)</div>
    <div class="card-text">
      IoT system that monitors temperature and humidity using ESP8266 + DHT11. Data is sent via MQTT, stored in SQLite, and displayed on a real-time dashboard.
    </div>
    <ul>
      <li>ESP8266 firmware publishing JSON via MQTT</li>
      <li>Python backend subscriber</li>
      <li>Local SQLite storage</li>
      <li>Real-time dashboard (Flask + Bootstrap + Chart.js)</li>
      <li>Modular and scalable structure</li>
    </ul>
    <div class="card-actions">
      <a class="btn btn-primary" href="https://github.com/renecano/IoT-Plant-Monitoring-System-ESP8266-MQTT-Flask-SQLite" target="_blank" rel="noopener">Repository</a>
      <a class="btn btn-ghost" href="/blog/projects/iot-plant-monitoring/">Read post</a>
    </div>
  </div>

  <div class="card">
    <div class="card-title">Fork/Join DAG Visualizer (Java + JavaFX)</div>
    <div class="card-text">
      Interactive tool that loads DAGs, renders them in JavaFX, and generates Fork/Join parallel code with execution simulation and validation.
      <span class="badge">Top 3 Prototype – Expo Ingeniería</span>
    </div>
    <ul>
      <li>Load DAGs from .txt adjacency matrices</li>
      <li>BFS-based level layout</li>
      <li>JavaFX rendering with animations</li>
      <li>Fork/Join code generation</li>
      <li>Execution simulation with branch coloring</li>
      <li>Structural validation (cycles, disconnected nodes, incorrect joins)</li>
    </ul>
    <div class="card-actions">
      <a class="btn btn-primary" href="https://github.com/renecano/grafos-fork-join-visualizer" target="_blank" rel="noopener">Repository</a>
      <a class="btn btn-ghost" href="/blog/projects/fork-join-dag-visualizer/">Technical breakdown</a>
    </div>
  </div>

</div>
