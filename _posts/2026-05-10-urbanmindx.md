---
layout: post
title: "UrbanMind X: Optimizing Urban Traffic with Reinforcement Learning"
description: "Design, training, and evaluation of a PPO-based RL agent for adaptive traffic signal control at a real Toluca intersection, achieving a 78.2% reduction in average wait time."
date: 2026-05-10
categories: blog projects
permalink: /blog/projects/urbanmindx/
---

UrbanMind X is a reinforcement learning system that controls traffic signals and autonomous vehicles at a real intersection in Toluca, México. It placed **1st at Expo Ingenierías 2026** at Tecnológico de Monterrey Campus Toluca.

---

## The problem

Traffic congestion in urban areas is largely a coordination problem. Fixed-cycle traffic lights don't adapt to real-time vehicle density — they follow rigid schedules regardless of whether an intersection is empty or saturated.

The intersection at **Pino Suárez × Ignacio Manuel Altamirano** in Toluca was chosen as the test case: a high-traffic crossing with significant peak-hour delays and no adaptive signal logic.

---

## Project objectives

- Design a simulation environment that accurately models the physical intersection
- Train an RL agent to minimize average vehicle wait time
- Evaluate performance against a fixed-cycle baseline
- Deploy a public-facing dashboard to visualize results

---

## Technologies used

- **SUMO** (Simulation of Urban MObility) for microsimulation
- **TraCI** for real-time agent–simulation communication
- **Gymnasium** for the custom RL environment wrapper
- **Stable-Baselines3** for the PPO implementation
- **Three.js + HTML/CSS** for the animated results dashboard
- **Netlify** for deployment

---

## System architecture

The environment wraps SUMO via TraCI inside a Gymnasium-compatible interface. At each step, the agent observes:

- Queue lengths per lane
- Current phase and elapsed phase time
- Accumulated waiting time

The PPO agent selects a traffic phase to activate. The reward function penalizes cumulative wait time and rewards smooth throughput.

Training ran for 300,000 timesteps. Early stopping was applied based on mean episode reward plateau.

---

## Results

| Metric | Fixed Cycle | UrbanMind X | Reduction |
|---|---|---|---|
| Avg. wait time | 303 s | 66 s | **78.2%** |
| Max queue length | 18 vehicles | 7 vehicles | 61.1% |
| Throughput | baseline | +34% | — |

The agent learned to extend green phases during dense inflows and shorten them when queues cleared — behavior that fixed cycles cannot replicate.

---

## Dashboard

A public dashboard was built and deployed at [anmindx.netlify.app](https://anmindx.netlify.app), featuring a Three.js animated intersection view, training curve charts, and a comparison panel between fixed-cycle and RL-controlled scenarios.

---

## Challenges and decisions

The main technical challenge was **reward shaping**: naive penalties for wait time caused the agent to oscillate between phases without committing to clearance. Adding a phase-change cost stabilized behavior.

Mapping the real intersection geometry into SUMO required manual calibration of lane widths, turn restrictions, and pedestrian crossings from satellite imagery.

---

## What I learned

- Designing simulation environments as Gymnasium wrappers
- Reward engineering for multi-objective RL problems
- The gap between simulation performance and real-world deployment constraints
- Communicating technical results to non-specialist audiences through visual design

---

## Next steps

- Multi-intersection coordination (networked agents)
- Real sensor data integration via traffic counters
- Transfer learning from simulation to real hardware controllers

---

**Repository:**  
https://github.com/renecano/urbanmindx

**Live dashboard:**  
https://anmindx.netlify.app

---

You can also explore:
- [All projects](/projects/)
- [More technical posts](/blog/)
