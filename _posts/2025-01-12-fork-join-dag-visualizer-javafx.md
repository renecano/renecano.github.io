---
layout: post
title: "Visualizing Parallelism with Fork/Join and DAGs (Java + JavaFX)"
date: 2025-12-12
categories: blog projects java concurrency
---

This project explores **parallelism and task coordination** by visualizing **Fork/Join execution** using **Directed Acyclic Graphs (DAGs)**.

The main idea was to transform an abstract concurrency model into a **visual, interactive tool** that helps understand how parallel tasks split and synchronize.

---

## The problem
Concurrency concepts such as **Fork/Join** are powerful but often difficult to understand when taught only through code.

I wanted to answer a simple question:
> *What if we could see parallel execution instead of only reading about it?*

---

## Project overview
The application takes a **DAG representation of tasks** and:

- Renders it visually using a layered layout  
- Identifies forks and joins automatically  
- Generates valid **Fork/Join Java code**  
- Simulates parallel execution step by step  

This turns theory into something observable and interactive.

---

## Technologies used
- **Java** for core logic  
- **JavaFX** for visualization and animations  
- **BFS-based layout algorithms** for node positioning  
- **Fork/Join Framework** concepts for code generation  

JavaFX was chosen to focus on clarity and control over the graphical representation.

---

## Key features
- Load DAGs from `.txt` adjacency matrices  
- Automatic level computation using BFS  
- Clean visual layout with animated nodes and edges  
- Automatic Fork/Join Java code generation  
- Parallel execution simulation with color-coded branches  
- Structural validation:
  - Cycles  
  - Disconnected nodes  
  - Incorrect fork/join structures  

---

## Design challenges
Two main challenges shaped this project:

### 1. Layout clarity
Placing nodes in a readable way required:
- Computing node depth levels  
- Grouping nodes by level  
- Centering siblings while avoiding overlaps  

A BFS traversal proved to be a simple and effective solution.

### 2. Validating graph structure
Not every graph represents valid parallel execution.

The system checks for:
- Cycles (which break Fork/Join logic)  
- Nodes without proper synchronization  
- Joins with incorrect task counts  

This made the tool closer to real-world engineering constraints.

---

## What I learned
This project strengthened my understanding of:
- Concurrency models and synchronization  
- Graph theory applied to software design  
- Visualization as a learning and debugging tool  
- Turning abstract concepts into concrete systems  

It also showed me how **visual feedback** can drastically improve understanding of complex systems.

---

## Recognition
This project was awarded **Top 3 Digital Prototype** at  
**Expo Ingeniería – Tecnológico de Monterrey, Campus Toluca**.

---

## Next steps
Future improvements could include:
- Supporting larger DAGs  
- Exporting execution traces  
- Interactive editing of graphs  
- Performance analysis of parallel execution  

---

**Repository:**  
https://github.com/renecano/grafos-fork-join-visualizer
