# 🚇 Smart Metro Rail Station Simulation

<p align="center">
  <strong>An Interactive 2D Computer Graphics Simulation of a Modern Metro Rail Station</strong>
</p>

<p align="center">
  Built with <strong>C++</strong> • <strong>OpenGL</strong> • <strong>GLUT</strong> • <strong>GLFW</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/C%2B%2B-17-blue?style=for-the-badge&logo=cplusplus" alt="C++17">
  <img src="https://img.shields.io/badge/OpenGL-2D%20Graphics-red?style=for-the-badge&logo=opengl" alt="OpenGL">
  <img src="https://img.shields.io/badge/GLUT-Graphics-orange?style=for-the-badge" alt="GLUT">
  <img src="https://img.shields.io/badge/Platform-macOS%20%7C%20Linux-lightgrey?style=for-the-badge" alt="Platform">
  <img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge" alt="Status">
</p>

---

## 📌 Overview

**Smart Metro Rail Station Simulation** is an interactive **2D Computer Graphics project** developed in C++ using OpenGL and GLUT/GLFW.

The project simulates a modern metro rail station with interactive train operations, platform screen doors, passenger movement, elevator and escalator systems, dynamic lighting, weather effects, signal control, multiple camera views, and a real-time HUD.

The simulation demonstrates how fundamental **Computer Graphics algorithms, geometric transformations, animation techniques, and event-driven interaction** can be combined to create a realistic transportation environment.

---

## 🎯 Project Objectives

- Demonstrate fundamental 2D Computer Graphics algorithms.
- Implement real-time animation using OpenGL.
- Simulate realistic metro train operations.
- Demonstrate geometric transformations.
- Create interactive environmental effects.
- Implement dynamic lighting and weather conditions.
- Simulate passenger and station infrastructure.
- Apply state-based logic to a graphical simulation.

---

# ✨ Features

## 🚆 Train Operations

The metro train supports a complete operational cycle:

- Train arrival
- Braking
- Stopping
- Door opening
- Passenger boarding
- Passenger exiting
- Door closing
- Train departure
- Emergency stop

---

## 🚪 Platform Screen Doors

A safety barrier system is implemented along the platform edge.

The platform screen doors:

- Remain locked while the train is moving.
- Synchronize with the train doors.
- Open only when the train is correctly positioned.
- Close before the train departs.
- Prevent passengers from crossing onto the track area.

---

## 👥 Passenger Simulation

Passengers are represented using simple animated 2D graphics.

The simulation includes:

- Passenger queuing
- Passenger movement
- Boarding
- Exiting
- Idle waiting
- Basic crowd movement

---

## 🛗 Elevator System

The station includes an animated elevator connecting the ground level and platform.

The elevator:

1. Travels between levels.
2. Stops at each floor.
3. Opens its doors.
4. Allows passengers to enter/exit.
5. Waits for a short period.
6. Closes its doors.
7. Reverses direction.

---

## 🪜 Escalator

A continuously animated escalator connects different station levels.

The steps move continuously to simulate real-world escalator operation.

---

## 🌤️ Dynamic Lighting

The environment supports three lighting conditions:

| Mode | Description |
|------|-------------|
| ☀️ Day | Bright daytime environment |
| 🌆 Evening | Transition lighting |
| 🌙 Night | Dark environment with station illumination |

The system includes:

- Sun
- Moon
- Station lights
- Smooth lighting transitions
- Environmental color changes

---

## 🌧️ Weather Effects

The simulation supports dynamic weather.

### Light Rain

Small amounts of rain are rendered throughout the environment.

### Heavy Rain

A denser rain effect is used to simulate severe weather.

### Fog

Fog can be toggled to reduce visibility and create atmospheric depth.

### Wet Surface

Rain can produce wet-surface reflections throughout the station environment.

---

## 🚦 Signal System

The station contains an interactive railway signal system.

Two modes are available:

- **Automatic Mode**
- **Manual Mode**

The signal state can respond automatically to the train's current operation or be controlled manually.

---

## 🏢 Station Infrastructure

The simulation includes:

- Railway tracks
- Elevated platform
- Platform screen doors
- Ticket counter
- Ticket gates
- Waiting area
- Benches
- Waiting shelter
- Elevator
- Escalator
- Station signboards
- Railway signals
- Digital clock
- Analog clock
- Metro train

---

# 🖥️ HUD & Interface

A real-time **Heads-Up Display (HUD)** provides:

- Current simulation state
- Train status
- Signal status
- Weather status
- Lighting mode
- Announcements
- Diagnostics information
- Keyboard controls

A control panel is also displayed inside the simulation.

---

# 🎮 Controls

| Key | Action |
|:---:|---|
| `A` | 🚆 Train arrives |
| `D` | 🚆 Train departs |
| `S` | 🛑 Emergency stop |
| `G` | 🚦 Change signal |
| `O` | 🚪 Open doors |
| `C` | 🚪 Close doors |
| `P` | ⏯️ Pause / Resume |
| `L` | 🌆 Evening preview |
| `N` | 🌙 Cycle Day → Evening → Night |
| `M` | 🚦 Toggle Auto / Manual signal |
| `F` | 🌫️ Toggle fog |
| `R` | 🌧️ Toggle light rain |
| `T` | ⛈️ Toggle heavy rain |
| `V` | 📷 Change camera view |
| `Esc` | ❌ Exit |

---

# 🎨 Computer Graphics Techniques

This project demonstrates several fundamental Computer Graphics concepts.

### Line Drawing Algorithms

- **DDA Line Drawing Algorithm**
- **Bresenham Line Drawing Algorithm**

### Circle Drawing

- **Midpoint Circle Algorithm**

### Geometric Transformations

- Translation
- Scaling
- Coordinate transformations

### Rendering

- OpenGL primitives
- Polygon rendering
- RGB color model
- Immediate-mode rendering

### Animation

- Frame-by-frame animation
- Timer-based animation
- Object movement
- State-based animation

---

# 🧠 Simulation Architecture

The main simulation is organized into the following sections:

```text
Metro.cpp
