# 🐤 Flappy Bird Clone (Godot 3.5.3)

A lightweight, mobile-optimized 2D arcade game built from scratch using the **Godot Engine 3.5.3 LTS** and **GDScript**. This project is a solo initiative designed to showcase core 2D game physics, procedural generation loops, and efficient code architecture for a professional development portfolio.

> ⚠️ **Project Status: Active Development (WIP)**  
> The core systems are currently being mapped out and built. This repository documents the step-by-step progress from structural design to a deployment-ready production build.

> This might take a while than expected since I want to progress and learn at pygame and the basics of Godot first. sorry not sorry

---

## 🚀 Key Highlights & Architectural Goals
* **Hardware-Optimized Development:** Built and profiled entirely on low-to-mid-range hardware (**Acer ES1-523**) to guarantee high performance, tight memory efficiency, and smooth 60 FPS gameplay on any device.
* **Modular Scene Architecture:** Leveraging Godot's node-scene inheritance to keep player mechanics, dynamic obstacles, and UI loops completely decoupled.
* **Pure GDScript Physics:** Custom-coded kinematic motion handling gravity curves and rapid upward propulsion vectors without relying on heavy engine overhead.

---

## 🛠️ Tech Stack
* **Engine:** Godot Engine 3.5.3 LTS
* **Language:** GDScript (Python-like scripting language)
* **Target Platforms:** Windows PC & Android Mobile

---

## 🎯 Implemented & Planned Features

### 🕹️ Core Game Mechanics
- [ ] **State-Driven Physics:** Custom `KinematicBody2D` implementation for responsive "flap" inputs and smooth gravity curves.
- [ ] **Procedural Obstacle Spawner:** Infinite, randomized pipe generation handling varying gap vectors on a continuous scroll wheel loop.
- [ ] **Precise Collision Matrix:** Clean collision layers setting apart the player, dangerous obstacles, and score-trigger zones.

### 📊 Systems & UI
- [ ] **Local Data Persistence:** High score data tracking saved via Godot’s file system (`user://`) so scores persist across sessions.
- [ ] **Adaptive UI/HUD:** Scalable `CanvasLayer` layout to accommodate both mobile aspect ratios and desktop windows.

---

## 📂 Project Architecture
The project follows a clean, decoupled directory structure typical of production-level Godot environments:
```text
├── assets/                  # Texture sprites, custom fonts, and audio elements
└── src/                     # Core source code and scene files
    ├── Global.gd            # Autoload singleton for score states and scene routing
    ├── Scenes/
    │   ├── MainGame.tscn    # Root world coordinator and spawner anchor
    │   ├── Bird.tscn        # Player object running KinematicBody2D loops
    │   ├── Pipe.tscn        # Reusable Area2D obstacle instances
    │   └── UI.tscn          # CanvasLayer HUD for reactive scoring
    └── project.godot        # Engine configuration file
```

---

## 📄 License

This project is a work-in-progress open-source utility licensed under the **MIT License**. See the [LICENSE](./LICENSE) file for the full copyright and permission notice.

