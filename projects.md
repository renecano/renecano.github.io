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

  <div class="card">
    <div class="card-title">Home Inventory System (Full-Stack App)</div>
    <div class="card-text">
      Full-stack home inventory management system to track products, consumption, and restocks, with minimum stock alerts and smart usage-based predictions.
    </div>
    <ul>
      <li>Product & stock management with minimum thresholds</li>
      <li>Consumption and restock history tracking</li>
      <li>Smart prediction of remaining stock days</li>
      <li>FastAPI REST backend + Next.js frontend</li>
      <li>Dockerized monorepo architecture</li>
    </ul>
    <div class="card-actions">
      <a class="btn btn-primary" href="https://github.com/renecano/home-inventory-system" target="_blank" rel="noopener">Repository</a>
      <a class="btn btn-ghost" href="/blog/projects/home-inventory-system/">Case study</a>
    </div>
  </div>

  <div class="card">
    <div class="card-title">UrbanMind X — Reinforcement Learning Traffic Control</div>
    <div class="card-text">
      PPO-based RL agent that optimizes traffic signals and autonomous vehicle flow at a real Toluca intersection, achieving a 78.2% reduction in average wait time.
      <span class="badge">1st Place – Expo Ingenierías 2026</span>
    </div>
    <ul>
      <li>PPO agent trained with Stable-Baselines3 + Gymnasium</li>
      <li>Real intersection simulation (Pino Suárez × Carranza) via SUMO/TraCI</li>
      <li>Wait time reduced from 303 s to 66 s (78.2%)</li>
      <li>Three.js animated dashboard deployed on Netlify</li>
      <li>APA 7 journal article + scientific poster</li>
    </ul>
    <div class="card-actions">
      <a class="btn btn-primary" href="https://github.com/renecano/urbanmindx" target="_blank" rel="noopener">Repository</a>
      <a class="btn btn-ghost" href="https://anmindx.netlify.app" target="_blank" rel="noopener">Live demo</a>
      <a class="btn btn-ghost" href="/blog/projects/urbanmindx/">Technical breakdown</a>
    </div>
  </div>

  <div class="card">
    <div class="card-title">CESVI RAT — Traffic Accident Reconstruction System</div>
    <div class="card-text">
      Full-stack forensic system for accident reconstruction and transit analysis, built for CESVI México. Handles deformation measurements, velocity calculations, and detailed incident reporting.
    </div>
    <ul>
      <li>54-table MySQL schema — designed and documented as DB coordinator</li>
      <li>Laravel backend with Eloquent models and migrations</li>
      <li>McHenry CRASH3 coefficients for forensic velocity estimation</li>
      <li>Cross-functional team: backend, frontend, QA, AI</li>
      <li>Full data dictionary + ERD delivered to client</li>
    </ul>
    <div class="card-actions">
      <a class="btn btn-primary" href="https://github.com/renecano/cesvi-rat" target="_blank" rel="noopener">Repository</a>
      <a class="btn btn-ghost" href="/blog/projects/cesvi-rat/">Case study</a>
    </div>
  </div>

</div>
