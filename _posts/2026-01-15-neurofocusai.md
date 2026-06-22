---
layout: post
title: "NeuroFocusAI: Real-Time Student Attention Analysis with Computer Vision"
description: "Design and implementation of a computer vision system that classifies student attention states in real time using MediaPipe facial landmarks, blink detection, and head pose estimation."
date: 2026-01-15
categories: blog projects
permalink: /blog/projects/neurofocusai/
---

NeuroFocusAI is a real-time attention monitoring system that uses a webcam and computer vision to classify a student's cognitive state during a learning session, then generates a summary dashboard of the full session.

---

## The problem

Educators have limited visibility into whether students are actually engaged during a session — especially in remote or self-paced learning environments. Fatigue and distraction often go undetected until performance drops.

The goal was to build a passive, non-invasive system that could infer attention states purely from a webcam feed, without any hardware sensors.

---

## Project objectives

- Detect facial landmarks in real time from a standard webcam
- Classify attention states based on eye behavior and head position
- Track state transitions over the full session
- Present results through a visual dashboard

---

## Technologies used

- **Python** for core application logic
- **OpenCV** for webcam capture and frame processing
- **MediaPipe** for 468-point facial landmark detection
- **HTML/CSS/JS** for the web dashboard interface

---

## System architecture

The project is organized into modular components:

```
src/
├── camera/      → webcam capture pipeline
├── detection/   → MediaPipe landmark extraction
├── analysis/    → eye analysis, head pose, state classification
├── ui/          → web dashboard and server
├── config.py    → thresholds and configuration
└── main.py      → main execution entry point
```

Each analysis module operates independently, which makes it easy to adjust thresholds or swap detection logic without touching the rest of the pipeline.

---

## State classification

The system detects four states:

| State | Key signals |
|---|---|
| Focused | Stable gaze, head aligned, low blink rate |
| Distracted | Gaze deviation or frequent head movement |
| Fatigued | High blink frequency, drooping eyelids |
| Stressed | Irregular blink patterns, tense landmarks |

Classification thresholds are configured in `config.py` and can be adjusted per use case.

---

## Dashboard

The web dashboard displays a per-session timeline of attention states, blink rate over time, gaze stability metrics, and an AI-generated summary of the session. It runs locally via a Flask-style web server.

---

## Challenges and decisions

The main challenge was **threshold calibration** — blink rate and head movement vary significantly between individuals, lighting conditions, and webcam quality. The solution was to make all thresholds configurable and add a short baseline calibration window at session start.

Choosing MediaPipe over a custom detector was a deliberate decision: the 468-point face mesh provides enough resolution for accurate eye aspect ratio and head pose calculations without requiring a GPU.

---

## What I learned

- Building real-time CV pipelines with per-frame state tracking
- Designing modular systems where analysis components are independent
- The difficulty of calibrating behavioral thresholds for diverse users
- Communicating continuous state data through clean visual design

---

## Next steps

- Per-user baseline calibration stored across sessions
- Integration with learning management systems (LMS)
- Mobile support via front-facing camera

---

**Repository:**  
https://github.com/renecano/NeuroFocusAI

---

You can also explore:
- [All projects](/projects/)
- [More technical posts](/blog/)
