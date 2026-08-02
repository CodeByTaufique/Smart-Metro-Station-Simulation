# 🚇 Smart Metro Rail Station Simulation

An interactive 2D Computer Graphics simulation of a modern metro rail station, built in **C++** with **OpenGL / GLUT / GLFW**. The project models realistic train arrival and departure, platform screen doors, passenger movement, a working elevator and escalator, dynamic day/evening/night lighting, and live weather effects — all driven by fundamental 2D graphics algorithms and a keyboard-controlled simulation loop.

---

## 📖 Overview

The simulation renders a full metro station scene: railway tracks, an elevated platform with safety doors, a ticket counter and gates, a waiting area, an elevator shaft, an escalator, station signage, a signal system, and a live HUD. A train can be dispatched, brought to a stop, and its doors opened and closed — with the platform's own screen doors and the passenger crowd responding to that state in real time, alongside a full day/night lighting cycle and rain/fog weather effects.

---

## ✨ Features

- 🚆 **Train operations** — arrival, braking, stopping, door open/close cycle, departure, and emergency stop
- 🚪 **Platform Screen Doors (safety system)** — glass barrier doors along the safety line that only unlock in sync with the train's own doors, preventing passengers from crossing to the track edge at any other time
- 🚶 **Passenger simulation** — queuing, boarding, exiting, and idle waiting passengers with simple animated movement
- 🛗 **Elevator** — a lift car that travels between the surface (ground level) and the platform, stopping at each floor to open its doors, dwell, and close again before reversing direction
- 🔼 **Escalator** — continuously animated step motion between levels
- 🌗 **Dynamic lighting** — Day / Evening / Night lighting modes with smooth transitions, sun/moon, and station lamp glow
- 🌧️ **Weather effects** — toggleable light rain, heavy rain, and fog, with wet-surface reflections
- 🚦 **Signal system** — automatic or manual signal control tied to train state
- 🏢 **Station infrastructure** — ticket counter, ticket gates, benches, waiting shelter, signboards, digital and analog clocks
- 🖥️ **HUD** — live announcements, on-screen console/diagnostics readout, and a controls reference panel
- 🎥 **Multiple camera views** — cycle between preset viewing angles
- 📐 **Core Computer Graphics techniques** — DDA Line Algorithm, Bresenham Line Algorithm, Midpoint Circle Algorithm, 2D geometric transformations (translation, scaling), the RGB color model, and frame-by-frame animation

---

## 🎮 Controls

| Key | Action |
|---|---|
| `A` | 🚆 Train arrives |
| `D` | 🚀 Train departs |
| `S` | 🛑 Emergency stop |
| `G` | 🚦 Change signal (manual mode) |
| `O` | 🔓 Open doors |
| `C` | 🔒 Close doors |
| `P` | ⏯️ Pause / resume simulation |
| `L` | 🌆 Evening preview |
| `N` | 🌗 Cycle Day → Evening → Night |
| `M` | 🤖 Toggle Auto / Manual signal mode |
| `F` | 🌫️ Toggle fog |
| `R` | 🌦️ Toggle light rain |
| `T` | ⛈️ Toggle heavy rain |
| `V` | 🎥 Cycle camera view |
| `Esc` | 🚪 Exit |

The full control list is also shown in-app via the bottom-left controls panel.

---

## 🧰 Requirements

- A C++17-capable compiler (e.g. `g++`, `clang++`)
- OpenGL
- GLUT (or FreeGLUT)
- GLFW (optional — the project also compiles against system GLUT alone)

### 🍎 macOS

```bash
brew install glfw glew
```
OpenGL and GLUT are provided by the system frameworks.

### 🐧 Linux (Debian/Ubuntu)

```bash
sudo apt install freeglut3-dev libglfw3-dev libglew-dev
```

---

## 🏗️ Building

### Option A — Direct compile

**macOS:**
```bash
clang++ -std=c++17 Metro.cpp -o Metro \
    -framework OpenGL -framework GLUT -framework Cocoa \
    -I/opt/homebrew/include -L/opt/homebrew/lib -lglfw -lGLEW
```

**Linux:**
```bash
g++ -std=c++17 Metro.cpp -o Metro -lGL -lGLU -lglut -lglfw -lGLEW
```

### Option B — CMake

If you're using CLion or prefer CMake, create a `CMakeLists.txt` alongside `Metro.cpp`:

```cmake
cmake_minimum_required(VERSION 3.16)
project(Metro)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)

add_executable(Metro Metro.cpp)
target_link_libraries(Metro OpenGL::GL GLUT::GLUT)
```

Then build:
```bash
mkdir build && cd build
cmake ..
cmake --build .
```

---

## ▶️ Running

```bash
./Metro
```

A window titled **"Smart Metro Rail Station Simulation | CG Lab Project"** will open. Use the keyboard controls above to interact with the station. 🎉

---

## 🗂️ Project Structure (single-file layout)

`Metro.cpp` is organized into clearly labeled sections:

1. 🔧 Global Constants
2. 🏷️ Enumerations
3. 🧱 Data Structures
4. 🌐 Global Simulation State
5. 📋 Function Prototypes
6. 📐 Core Graphics Algorithms
7. 🔄 2D Geometric Transformations
8. 💡 Lighting Palette System
9. 🌳 Environment
10. 🐦 Optional Enhancements — Birds, Wind & Multi-Station
11. 🏢 Metro Infrastructure
12. 🚆 Metro Train
13. 🚶 Human Elements
14. 🌧️ Weather Effects
15. 🖥️ Heads-Up Display
16. ⚙️ Simulation State Machine
17. 🎥 Camera / Projection
18. ⌨️ Keyboard Input Handling
19. 🔁 GLUT Callbacks
20. 🚀 Program Entry Point

---

## 📝 Notes

- Legacy OpenGL (`glBegin`/`glEnd`, immediate mode) is used throughout for simplicity and compatibility with GLUT — this produces deprecation warnings on macOS but does not affect functionality.
- All animation (train, doors, elevator, escalator, weather, lighting transitions) is advanced on a fixed simulation tick via `glutTimerFunc`.

---

## 🎓 Academic Context

This project was developed as a Computer Graphics (CG) Lab course project, demonstrating the practical application of 2D rendering algorithms, geometric transformations, and interactive animation in a real-world-inspired transportation simulation.
