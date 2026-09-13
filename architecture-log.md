# 📓 Project Architecture & Development Log

This document covers the engineering design, technical constraints, and architectural planning for this 2D Flappy Bird implementation in **Godot 3.5.3 LTS**. 

---

## 1. Project Background & Motivation

### The Challenge of Resource-Constrained Development
When starting out in game development, hardware limitations and engine bloat can be massive bottlenecks. Many modern commercial engines demand high-end system specifications, which creates an artificial barrier to entry. 

This project explores how a developer can leverage lightweight, highly optimized open-source tools to build stable 2D experiences without sacrificing modern coding standards. 

* **Development Hardware:** Acer ES1-523 (Low-to-mid range baseline environment)
* **The Goal:** Build a fully modular, 60 FPS mobile/desktop game while working completely within these tight system constraints.

### Why Flappy Bird?
While the gameplay loop of *Flappy Bird* is mechanically simple, its underlying system architecture relies on three foundational concepts crucial to any production-level 2D game engine:
1. **Physics Simulation:** Constant downward acceleration (gravity vectors) countered by deterministic, instantaneous velocity shifts (flap impulse).
2. **Procedural Runtime Generation:** Object pooling and spawning logic to handle endless, randomized obstacles while keeping memory overhead flat.
3. **Discrete Collision Matrices:** Decoupled scoring vectors, environmental boundary collisions, and instant game-over triggers.

---

## 2. Core Constraints & Technical Scope

To ensure a delivery window of **one month** and prevent scope creep, the implementation adheres to strict architectural boundaries:

### Included Systems (In-Scope)
* **Kinematic Physics:** Accurate state handling for player movement.
* **Dynamic Obstacle Generation:** Script-driven spawning cycles on a continuous, variable coordinate loop.
* **Layered Collision Matrix:** Dedicated collision layers dividing player hurtboxes, environmental static boundaries, and passive scoring triggers.
* **Platform Deployments:** Native compile targets for Windows PC and Android mobile deployment.

### Excluded Elements (Out-of-Scope)
* Network infrastructure, multiplayer synchronization, or online databases.
* Heavy graphical assets, shader overhead, or 3D viewports.
* Commercial frameworks, analytics tracking, or in-app monetization hooks.

---

## 3. Technology Stack Choice

### Godot Engine 3.5.3 LTS
Godot was selected over heavy alternatives (like Unity or Unreal) due to its specialized architectural benefits:
* **Micro File Footprint:** Extremely small engine overhead allows for instant iteration cycles on low-spec hardware.
* **Modular Scene-Tree Paradigm:** Everything is a Node. This allows entities like the Bird, individual Pipes, and UI canvases to live in completely isolated scenes, preventing code dependency tangles.
* **GDScript Performance:** GDScript's low overhead and Python-like syntax make it excellent for writing clear, readable code logic that processes physics efficiently at runtime.

---

## 4. Engineering Roadmap

The development workflow is broken down sequentially into the following execution phases:

```text
 ┌───────────────┐      ┌───────────────┐      ┌──────────────────┐
 │ 1. Planning   │ ───> │ 2. Project    │ ───> │ 3. Core Mechanics│
 │ (Scope & Spec)│      │    Setup      │      │ (Physics & Loops)│
 └───────────────┘      └───────────────┘      └──────────────────┘
                                                         │
                                                         ▼
 ┌───────────────┐      ┌───────────────┐      ┌──────────────────┐
 │ Final Release │ <─── │  5. Target    │ <─── │ 4. Profiling &   │
 │ & Documentation│     │  Compilations │      │    Debugging     │
 └───────────────┘      └───────────────┘      └──────────────────┘
```

1. **Planning:** Architecture design, directory mapping, and state definition *(Complete)*.
2. **Project Setup:** Node configuration, input map declarations, and project property adjustments.
3. **Core Mechanics:** Coding the discrete GDScript modules for motion, procedural spawning, and UI loops.
4. **Profiling & Debugging:** Running execution passes on the Acer ES1-523 to catch memory leaks, bad object instancing, or frame drops.
5. **Target Compilations:** Packaging isolated release builds for desktop execution environments and mobile packages.
